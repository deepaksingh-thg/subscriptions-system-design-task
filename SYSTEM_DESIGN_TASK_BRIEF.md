# System Design Task: Subscription Service

You are designing a Subscription Service for an ecommerce platform.

The Subscription Service is the source of truth for subscription state. It is responsible for creating subscriptions during checkout, orchestrating recurring order generations, and managing the subscription lifecycle.

You do not need to produce a perfect architecture. Focus on the overall design, service interactions, data ownership, failure handling, and the trade-offs behind your decisions.

---

## Context

A subscription contains:

* Customer ID
* Product SKU and quantity
* Delivery frequency
* Next order generation trigger date
* Status (e.g. Active, Paused, Cancelled)
* Payment token reference
* Shipping address reference

---

## Existing Services

Assume the following services already exist:

* **Checkout** – orchestrates the customer purchase journey
* **Payment** – charges customers and stores payment tokens
* **Order Management** – creates and fulfils orders
* **Stock** – checks product availability
* **Notification** – sends emails and SMS
* **Asynchronous Messaging Platform** – supports event-driven communication

---

## Your Task

Talk through how you would design the Subscription Service, and how it would fit against those existing services.

Start wherever feels natural, but aim to cover all four areas below.

---

### 1. Subscription Creation

Describe what happens when a customer purchases a subscription for a physical product during checkout.

Explain:

* How existing services and the Subscription Service interact
* Synchronous versus asynchronous communication
* What data is stored by the Subscription Service
* What events are published
* How failures are handled

---

### 2. Recurring Order Generation Processing

Describe how scheduled recurring order generations are processed.

Consider:

* How order generations are triggered
* Which services participate
* Synchronous versus asynchronous communication
* The overall data flow
* The final outcome of a successful order generation

---

### 3. Failure Recovery

Explain how your design recovers from failures such as:

* Payment failures
* Products becoming unavailable
* Duplicate requests or scheduler retries
* Partial failures between services

Describe how the system remains consistent and recovers safely.

---

### 4. Running the Service

Describe how you would operate this service in production.

Consider topics such as:

* State management
* Monitoring and alerting
* Scalability
* High availability
* Infrastructure choices

---

## Notes

You are not expected to define detailed APIs or database schemas.

A high-level discussion supported by simple sketches or diagrams is sufficient.

We are interested in your reasoning, trade-offs, and how you approach designing reliable distributed systems.
