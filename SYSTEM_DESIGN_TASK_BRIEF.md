# System Design Task: Subscription Service

You are designing a **Subscription Service** for an ecommerce platform.

The Subscription Service is the **source of truth for subscription state**. It creates subscriptions during checkout, generates recurring orders, and manages the subscription lifecycle.

---

## Context

A subscription contains:

- Customer ID
- Product SKU and quantity
- Delivery frequency
- Next order generation date
- Status (e.g. Active, Paused, Cancelled)
- Payment token reference
- Shipping address reference

### Existing Services

Assume the following services already exist:

- **Checkout** – orchestrates the customer purchase journey
- **Payment** – charges customers and stores payment tokens
- **Order Management** – creates and fulfils orders
- **Stock** – checks product availability
- **Notification** – sends emails and SMS
- **Asynchronous Messaging Platform** – supports event-driven communication

---

## Your Task

Talk through how you would design the Subscription Service and how it interacts with the existing services.

### 1. Subscription Creation

Describe what happens when a customer purchases a subscription.

Consider:

- How the services interact
- What should be synchronous vs asynchronous
- What the Subscription Service owns and stores

### 2. Recurring Order Generation

Describe how recurring orders are generated for active subscriptions.

Consider:

- How due subscriptions are identified and triggered
- Which services are involved
- What a successful recurring order flow looks like

### 3. Failure Handling

Explain how your design handles scenarios such as:

- Payment failures
- Products becoming unavailable
- Duplicate or retried requests
- Partial failures between services

### 4. Running the Service

Describe how you would operate the service in production.

Consider:

- State management
- Monitoring and alerting
- Scalability and high availability
- Infrastructure choices

---

## Notes

You do not need to define detailed APIs or database schemas.

A high-level diagram and discussion of your design decisions and trade-offs is sufficient.
