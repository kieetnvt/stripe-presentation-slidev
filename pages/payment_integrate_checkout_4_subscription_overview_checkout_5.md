---
layout: default
transition: slide-left
---

## Stripe Checkout: Set the billing cycle date

```ruby
session = Stripe::Checkout::Session.create(
  line_items: [{
    price: '{{PRICE_ID}}',
    quantity: 1,
  }],
  mode: 'subscription',
  success_url: 'https://example.com/success?session_id={CHECKOUT_SESSION_ID}',
  cancel_url: 'https://example.com/cancel',
  subscription_data: { billing_cycle_anchor: 1701446593 }, # 01/12/2023}
)
```