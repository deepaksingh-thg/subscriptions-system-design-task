## Your Task

Design the **Subscription Service** and show how it interacts with the existing services.

Start by drawing the high-level service flow for these two scenarios:

### A. Initial Subscription Purchase

A customer has selected a subscription product and reaches Checkout.

Show how:

- Checkout
- Stock
- Payment
- Subscription Service
- Order Management
- Notification

interact to complete the purchase.

Explain which interactions are synchronous or asynchronous and what state is owned by Subscription Service.

### B. Recurring Order

The subscription reaches its next order generation date.

Show how Subscription Service triggers the next order without the customer going through Checkout again.

Explain:

- how the renewal is triggered
- stock validation
- payment
- order creation
- subscription state updates
- notifications

### C. Failure Handling

Using the design above, explain how you would handle:

- payment failure
- out-of-stock products
- duplicate/retried requests
- partial service failures

### D. Production Operation

Briefly discuss:

- monitoring and alerting
- scalability and availability
- infrastructure choices
