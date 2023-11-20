---
layout: full
transition: slide-left
title: Payment Intents Lifecycle
---

Integrate Steps: [API Payment Intents](https://stripe.com/docs/payments/payment-intents)

1. Creating a PaymentIntent

```ruby
Stripe::PaymentIntent.create({
  amount: 1099,
  currency: 'usd',
  payment_method_types: ['card'],
})
```

2. Passing the client secret to the client side, init form payment => add payment method and confirm payment

```
get '/secret' do
  intent = # ... Create or retrieve the PaymentIntent
  {client_secret: intent.client_secret}.to_json
end
```

```javascript
(async () => {
  const response = await fetch('/secret');
  const {client_secret: clientSecret} = await response.json();
  // Render the form using the clientSecret
})();
```

3. After the client confirms the payment, it is a best practice for your server to monitor webhooks to detect when the payment successfully completes or fails.

