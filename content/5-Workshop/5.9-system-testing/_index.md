---
title : "Testing the System After Deployment"
date : 2024-01-01
weight : 9
chapter : false
pre : " <b> 5.9. </b> "
---

## Objective

This step tests AWS_OmniStay after the backend, frontend, CloudFront, WAF, and monitoring have been deployed. The goal is to prove that the website can be accessed from the public Internet, the API works through CloudFront, the backend can connect to RDS and Redis, and operational components such as the ALB, Target Group, and CloudWatch have correct data.

## 1. Check Health Through CloudFront

Open the browser or use an HTTP request tool:

```text
https://<cloudfront-domain>/health
https://<cloudfront-domain>/health/aws
```

Expected result from `/health/aws`:

```text
environment = Production
databaseProvider = MySql
redisConfigured = true
redisConnected = true
apiBasePath = /api
```

If a `403` error occurs, check whether the `/health*` behavior points to the ALB. If a `502` or `504` error occurs, check the Target Group, ALB origin DNS, and ALB Security Group.

![VPC details](/images/591.jpg)
<p align="center"><em>Figure 5.9.1: Browser successfully displays `/health/aws` through CloudFront.</em></p>

## 2. Check the Search API Through CloudFront

Call the hotel search API:

```text
https://<cloudfront-domain>/api/hotels/search?city=Da%20Nang&checkIn=2026-12-10&checkOut=2026-12-12&guests=2
```

Expected result:

- The API returns HTTP 200.
- The response is a JSON array.
- Hotel data is returned if seed data has been loaded.
- No `403`, `502`, `503`, or `504` error occurs.

If the API fails, check the CloudFront `/api/*` behavior, allowed methods, query string forwarding, and the `CachingDisabled` cache policy.

## 3. Check the Public Website Interface

Open the frontend page:

```text
https://<cloudfront-domain>/public/index.html
```

Suggested test flow:

1. Open the login page or home page.
2. Log in as admin using the demo account, but do not write the password in the report.
3. Go to the Admin page and verify that users, hotels, and bookings load correctly.
4. Log out.
5. Register a new customer account.
6. Search for hotels in `Da Nang`.
7. Select a hotel from the search results.
8. Book a room.
9. Complete the payment/mock payment step based on the available function.
10. Go to the booking history page to verify that the booking was recorded.

![VPC details](/images/592.jpg)
<p align="center"><em>Figure 5.9.2: Public login page or home page.</em></p>

## 4. Check Redis Cache Evidence

Call the same search URL twice:

```text
https://<cloudfront-domain>/api/hotels/search?city=Da%20Nang&checkIn=2026-12-10&checkOut=2026-12-12&guests=2
```

Then check backend logs on EC2:

```bash
sudo journalctl -u omnistay-api -n 300 --no-pager
```

Expected result:

```text
Hotel search cache MISS
Hotel search cache HIT
```

The first request is usually a cache MISS because the data is not yet in Redis. The second request is a cache HIT if Redis is working correctly and the TTL has not expired.

## 5. Check RDS Evidence

Go to **RDS** -> **Databases** -> `omnistay-mysql`.

Check the following:

- Database status is `Available`.
- Endpoint and port match the backend configuration.
- Security Group is `SG-RDS`.
- Metrics contain CPU and database connection data.

If a database query tool is available, check the main business tables:

```text
Users
Hotels
RoomTypes
Bookings
```

## 6. Check ALB and Target Group Evidence

Go to **EC2** -> **Target Groups** -> `omnistay-api-tg`.

Expected values:

```text
Target health: Healthy
Health check path: /health
Port: 8080
```

Go to **EC2** -> **Load Balancers** -> `omnistay-alb`.

Expected values:

- ALB state is `Active`.
- Scheme is `Internet-facing`.
- Listener HTTP 80 forwards to `omnistay-api-tg`.
- ALB DNS name is available.

## 7. Check the CloudWatch Dashboard

Go to **CloudWatch** -> **Dashboards** -> `OmniStay-Demo`.

After generating traffic by accessing the frontend and calling APIs, the dashboard should have data for:

- ALB request count.
- ALB 5XX count.
- EC2 CPU utilization.
- ASG desired/in-service instances.
- RDS connections.
- Redis connections.

## 8. Post-deployment Acceptance Checklist

| Item | Expected result |
| --- | --- |
| CloudFront frontend | Public website can be accessed |
| CloudFront `/api/*` | Correctly forwards to ALB |
| CloudFront `/health*` | Returns health check from backend |
| ALB | Active, HTTP 80 listener works |
| Target Group | EC2 target is healthy |
| Backend service | `omnistay-api` is active on EC2 |
| RDS | Backend connects to MySQL successfully |
| Redis | Search shows cache HIT/MISS |
| WAF | Attached to CloudFront and does not block valid flows |
| CloudWatch | Dashboard and alarms are created |

## Expected Result

After testing, the AWS_OmniStay system has complete evidence for the frontend, API, backend, database, cache, load balancing, and monitoring flows. The screenshots in this section are important proof that the website and system deployment have been completed step by step.
