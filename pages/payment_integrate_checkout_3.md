---
layout: default
transition: slide-left
---

## Stripe Checkout: Embedded form

1. When a customer is ready to complete their purchase, your application creates a new Checkout Session.

2. <b>You mount Checkout as an embeddable component on your website to show a payment form.</b>

3. Customers enter their payment details and complete the transaction.

4. After the transaction, the checkout.session.completed webhook event triggers the order fulfillment process.

