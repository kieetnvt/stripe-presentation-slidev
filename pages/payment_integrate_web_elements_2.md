---
layout: full
transition: slide-left
---

## Payment Element

The Payment Element is a UI component for the web that accepts 40+ payment methods, validates input, and handles errors. Use it alone or with other elements in your web app’s frontend.

Steps:

1. Create a Payment Element

```javascript
const stripe = Stripe('pk_test_51OADTuE2rkCMN6VCtvF0CSosbS4GWpCbapUY6bpfvTonxLIv7nQDQt5ZIIgmCMKaEEsGdODisbYvuehraj5ydG1X00OILYsn69');

const appearance = { /* appearance */ };
const options = { /* options */ };
const elements = stripe.elements({ clientSecret, appearance });
const paymentElement = elements.create('payment', options);
paymentElement.mount('#payment-element');

```
