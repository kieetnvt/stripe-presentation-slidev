---
layout: default
transition: slide-left
---

## Displaying the 3D Secure Flow

Stripe automatically displays the authentication UI in a pop-up modal when calling `confirmCardPayment` and `handleCardAction`. You can also redirect to the bank’s website or use an iframe.

1. Redirect to the bank website

- To redirect your customer to the 3DS authentication page, pass a `return_url` to the `PaymentIntent` when confirming on the server or on the client.

```javascript
stripe
  .confirmCardPayment('{PAYMENT_INTENT_CLIENT_SECRET}', {
    payment_method: {
      card: cardElement,
      billing_details: {
        name: 'Jenny Rosen',
      },
      return_url: 'https://mysite.com'
    },
  })
  .then(function(result) {
    // Handle result.error or result.paymentIntent
  });
```
