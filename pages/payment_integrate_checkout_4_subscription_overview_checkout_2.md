---
layout: default
transition: slide-left
---

## Stripe Checkout: Subscription overview & flow

After payment for subscription success, the customer returns to your success page, a `checkout.session.completed` webhooks will be call to your server.

Each month (if billing monthly), `invoice.paid` webhook will be call to your server and `invoice.payment_failed` will be call when payment failed (card insufficient issue for example)

```ruby
  # Get the type of webhook event sent
  event_type = event['type']
  data = event['data']
  data_object = data['object']

  case event_type
  when 'checkout.session.completed'
    # Payment is successful and the subscription is created.
    # You should provision the subscription and save the customer ID to your database.
  when 'invoice.paid'
    # Continue to provision the subscription as payments continue to be made.
    # Store the status in your database and check when a user accesses your service.
    # This approach helps you avoid hitting rate limits.
  when 'invoice.payment_failed'
    # The payment failed or the customer does not have a valid payment method.
    # The subscription becomes past_due. Notify your customer and send them to the
    # customer portal to update their payment information.
  end
```
