#  BugPulse — RESTful API Validation & Defect Intelligence Dashboard

 API testing project for a Flutter e-commerce backend — validating CRUD operations, authentication, and edge cases using Postman, with a custom defect tracking dashboard built in Excel.



##  Project Overview

BugPulse focuses on backend API quality assurance for a Flutter e-commerce application. The project involved testing all RESTful endpoints across two sprints, tracking defects by severity and status, and building a dashboard to monitor resolution timelines.

**Role:** QA Tester  
**Testing Type:** API Testing (Manual)  
**Tools:** Postman, Excel  





##  What Was Tested

### CRUD Operations Validated
- `POST /api/auth/register` — User registration
- `POST /api/auth/login` — Token-based authentication
- `GET /api/products` — Product listing with pagination
- `POST /api/products` — Product creation (auth enforcement)
- `GET /api/products/:id` — Product by ID
- `GET /api/products/search` — Search with query params
- `POST /api/cart` — Add to cart
- `GET /api/cart` — Retrieve cart
- `DELETE /api/cart/:itemId` — Remove from cart
- `POST /api/orders` — Place order
- `GET /api/orders/:id` — Order details
- `GET /api/orders` — Order history

### Testing Techniques
- **Positive Testing** — Valid inputs, expected happy paths
- **Negative Testing** — Invalid IDs, missing auth, wrong data types
- **Boundary Testing** — Quantity 0, empty strings, special characters
- **Security Spot-checks** — Unauthenticated access to protected endpoints



##  Defects Found

| Bug ID | Endpoint | Title | Severity | Status |
|---|---|---|---|---|
| DEF001 | POST /products | Product creation accessible without auth |  Critical | Open |
| DEF002 | GET /products/search | 500 error on special character input | Critical | In Progress |
| DEF003 | POST /cart | Cart accepts item with quantity 0 |  Major | Open |
| DEF004 | GET /products | Pagination not working |  Minor |  Closed |
| DEF005 | POST /auth/login | Token expiry not validated on refresh |  Major | Open |


## 🛠️ Tools Used
| Postman | API request testing and validation |
| Excel | Defect tracking dashboard |
| JIRA | Sprint and bug lifecycle management |
| Git / GitHub | Version control and portfolio |



##  Key Takeaways

- Discovered a **critical security vulnerability** — product creation endpoint had no authentication guard
- Identified a **server crash** on special character input in search, preventing SQL/NoSQL injection risks
- Built a **defect dashboard** tracking severity, sprint, and resolution status across 2 sprints
- Reported **5 defects** across 17 endpoints with clear reproduction steps for the dev team



