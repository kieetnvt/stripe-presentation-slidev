---
layout: default
transition: slide-left
---

## Webhooks

Server create webhook endpoint to handle payload data from Stripe

```ruby
class WebhookController < ActionController::Base
  skip_before_action :verify_authenticity_token

  def stripe
    data = params['data']['object']

    case params['type']
    when 'invoice.paid'
      if data['billing_reason'].freeze == 'subscription_cycle'
        StripeSubscription::Webhook::RenewalService.new(data).process
      end
    when 'customer.subscription.updated'
      StripeSubscription::Webhook::UpdatedService.new(data).process
    end

    render json: { status: 'ok' }, status: :ok
  end
end
```

