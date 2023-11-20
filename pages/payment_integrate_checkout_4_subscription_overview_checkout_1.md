---
layout: default
transition: slide-left
---

## Stripe Checkout: Subscription overview & flow

```ruby
session = Stripe::Checkout::Session.create({
  success_url: 'https://example.com/success.html?session_id={CHECKOUT_SESSION_ID}',
  cancel_url: 'https://example.com/canceled.html',
  mode: 'subscription',
  line_items: [{
    # For metered billing, do not pass quantity
    quantity: 1,
    price: price_id,
  }],
})
```

![subscription created](/images/subscription-created.png)