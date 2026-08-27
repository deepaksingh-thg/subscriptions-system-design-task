# System Design Task: Subscription Service

You are designing a **Subscription Service** for an ecommerce platform.

You do not need to produce a perfect architecture. We are interested in your reasoning, design decisions, trade-offs, and how you approach building reliable distributed systems.

---

## Context

The ecommerce platform supports **Subscribe & Save** style subscriptions for physical products.

For example, a customer might purchase a bag of protein powder and choose to receive the same product every 30 days.

When the customer first checks out, an initial order is created. The Subscription Service then keeps track of the subscription and is responsible for initiating future recurring orders based on the customer's chosen frequency.

The customer does not need to return to Checkout for each recurring order.

The **Subscription Service is the source of truth for subscription state**.

A subscription contains:

- Customer ID
- Product SKU and quantity
- Delivery frequency
- Next order generation date
- Status (e.g. Active, Paused, Cancelled)
- Payment token reference
- Shipping address reference

---

## Existing Services

Assume the following services already exist:

- **Checkout** – orchestrates the customer's initial purchase journey
- **Payment** – charges customers and stores payment tokens
- **Order Management** – creates and fulfils orders
- **Stock** – checks product availability
- **Notification** – sends emails and SMS
- **Asynchronous Messaging Platform** – supports event-driven communication

Your task is to design the **Subscription Service** and show how it interacts with these existing services.

---

## 1. Initial Subscription Purchase

A customer has selected a subscription product and reaches Checkout.

Draw a high-level service interaction diagram showing how the initial purchase is completed.

Consider how the following services interact:

- Checkout
- Stock
- Payment
- Subscription Service
- Order Management
- Notification

As you walk through the design, explain:

- Which interactions should be synchronous or asynchronous
- What data the Subscription Service owns and how it persists that data
- What happens when the purchase successfully completes

---

## 2. Recurring Order Generation

The subscription eventually reaches its next order generation date.

Show how the Subscription Service generates the next order **without the customer going through Checkout again**.

Consider:

- How due subscriptions are identified and triggered
- Stock availability
- Payment
- Order creation
- Subscription state updates
- Customer notifications

Explain the overall flow and what the system should look like after a successful recurring order.

---

## 3. Failure Handling

Using your design above, explain how the system handles scenarios such as:

- Payment failures
- Products becoming unavailable
- Duplicate or retried requests
- Partial failures between services

Consider how the system remains consistent and how failed operations can be safely retried or recovered.

---

## 4. Running the Service

Briefly describe how you would operate the Subscription Service in production.

Consider:

- Database choice and consistency
- Monitoring and alerting
- Scalability and high availability
- Infrastructure choices

---

## Notes

You are **not** expected to define detailed APIs or database schemas.

A high-level diagram supported by a discussion of your design decisions and trade-offs is sufficient.
