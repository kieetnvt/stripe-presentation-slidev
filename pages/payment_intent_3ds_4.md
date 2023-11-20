---
layout: default
transition: slide-left
---

## Card authentication and 3D Secure

- The default method to trigger 3DS is using Radar to dynamically request 3D Secure based on risk level and other requirements.

- To trigger 3DS manually, set `payment_method_options[card][request_three_d_secure]` to any when creating or confirming a PaymentIntent or SetupIntent.

- When you set `request_three_d_secure` to `any`, Stripe requires your customer to perform authentication to complete the payment successfully if 3DS authentication is available for a card.

- If it’s not available for the given card, the payment proceeds normally.