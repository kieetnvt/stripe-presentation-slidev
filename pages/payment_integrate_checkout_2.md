---
layout: default
transition: slide-left
---

## Stripe Checkout: Stripe-hosted page

1. When customers are ready to complete their purchase, your application creates a new Checkout Session.

2. The Checkout Session provides a URL that redirects customers to a Stripe-hosted payment page.

3. Customers enter their payment details on the payment page and complete the transaction.

4. After the transaction, a webhook fulfills the order using the checkout.session.completed event.
