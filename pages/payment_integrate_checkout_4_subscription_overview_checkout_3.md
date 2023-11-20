---
layout: default
transition: slide-left
---

## Stripe Checkout: Subscription overview & flow

Trials

```ruby
Stripe::Checkout::Session.create({
  mode: 'subscription',
  success_url: 'https://example.com/success',
  cancel_url: 'https://example.com/cancel',
  line_items: [
    {
      price: '{{PRICE_ID}}',
      quantity: 1,
    },
  ],
  subscription_data: {
    trial_settings: {end_behavior: {missing_payment_method: 'cancel'}},
    trial_period_days: 30,
  },
  payment_method_collection: 'if_required',
})
```