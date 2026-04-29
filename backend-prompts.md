# Backend Prompts (Node.js)

Reusable two-liner prompts for common backend tasks and features.

---

## Project Setup

**Express App Scaffold**

```
Set up an Express app with a clean folder structure — routes, controllers, services, and middleware layers.
Follow the layered architecture pattern — keep HTTP concerns in controllers and business logic in services.
```

**Environment Config**

```
Create a centralized config module that loads environment variables with defaults and validation.
Follow the singleton pattern — export a frozen config object so values are read once and reused everywhere.
```

---

## Authentication & Authorization

**JWT Authentication**

```
Implement JWT-based auth with login, token generation, and a middleware that verifies tokens on protected routes.
Follow the middleware-chain pattern — validate the token early in the pipeline and attach the user to the request.
```

**Role-Based Access Control**

```
Create an authorization middleware that checks the authenticated user's role against allowed roles for a route.
Follow the guard/policy pattern — define permissions per route and reject unauthorized requests before reaching the controller.
```

**Password Hashing**

```
Add secure password hashing on registration and comparison on login using bcrypt.
Follow the service-layer pattern — keep hashing logic in an auth service, never in the controller or model directly.
```

---

## API Design

**RESTful CRUD Endpoints**

```
Build a full CRUD (create, read, update, delete) route set for a resource with proper HTTP methods and status codes.
Follow the resource-controller pattern — one controller per resource, one method per operation, consistent response shape.
```

**Request Validation**

```
Add request validation middleware using Joi or Zod that checks body, params, and query before the handler runs.
Follow the schema-first pattern — define the expected shape upfront and reject invalid requests with clear error messages.
```

**Pagination & Filtering**

```
Add pagination (limit/offset or cursor) and filtering support to a list endpoint.
Follow the query-builder pattern — translate query params into database query options in the service layer.
```

---

## Database

**Database Connection**

```
Set up a database connection (MongoDB/PostgreSQL) with a connection pool and graceful shutdown handling.
Follow the singleton pattern — initialize the connection once at startup and export it for use across modules.
```

**Data Model / Schema**

```
Define a data model with field types, required fields, defaults, and indexes.
Follow the active-record or repository pattern — encapsulate all data access for a model in one place.
```

**Database Migration**

```
Create a migration script that applies schema changes (add table, add column, seed data) in a versioned, repeatable way.
Follow the versioned-migration pattern — each migration has an up and down function and runs in order.
```

---

## Middleware

**Error Handling Middleware**

```
Create a centralized error-handling middleware that catches all errors and returns a consistent JSON response.
Follow the chain-of-responsibility pattern — let errors bubble up and handle them in one place at the end of the stack.
```

**Request Logging**

```
Add a request logging middleware that logs method, URL, status code, and response time for every request.
Follow the interceptor pattern — hook into the request lifecycle early and log on response finish.
```

**Rate Limiting**

```
Add rate limiting middleware that caps requests per IP within a time window and returns 429 on excess.
Follow the throttle pattern — use a sliding window or token bucket algorithm and store counts in memory or Redis.
```

---

## File Handling

**File Upload**

```
Implement a file upload endpoint using Multer with size limits, file type filtering, and storage config.
Follow the middleware pattern — process the file in middleware before the controller handles the business logic.
```

**Static File Serving**

```
Serve static files (images, documents) from a designated directory with proper cache headers.
Follow the convention-over-configuration pattern — map a URL prefix to a folder and let Express handle the rest.
```

---

## Background Jobs & Scheduling

**Background Job Queue**

```
Set up a simple job queue (using Bull or a lightweight in-memory queue) for offloading long-running tasks.
Follow the producer-consumer pattern — enqueue jobs from the API layer and process them in a separate worker.
```

**Scheduled Task / Cron**

```
Create a scheduled task that runs at a fixed interval (e.g., cleanup, report generation) using node-cron.
Follow the scheduler pattern — define the schedule and handler in a dedicated module, initialized at app startup.
```

---

## Security

**Input Sanitization**

```
Add middleware that sanitizes incoming request data to prevent XSS and injection attacks.
Follow the filter pattern — clean all user input at the entry point before it reaches any handler.
```

**CORS Configuration**

```
Configure CORS middleware with an explicit allowlist of origins, methods, and headers.
Follow the whitelist pattern — deny by default and only allow known, trusted origins.
```

**Helmet Security Headers**

```
Add Helmet middleware to set secure HTTP headers (CSP, X-Frame-Options, HSTS, etc.) on all responses.
Follow the defense-in-depth pattern — apply security headers globally as a baseline protection layer.
```

---

## Testing

**API Endpoint Test**

```
Write an integration test for an endpoint using Supertest — send a request, assert status code and response body.
Follow the arrange-act-assert pattern and use a test database or mocks to isolate from production data.
```

**Service Unit Test**

```
Write a unit test for a service function — mock its dependencies, call the function, and assert the result.
Follow the isolation pattern — test pure business logic without spinning up the server or database.
```
