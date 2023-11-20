---
layout: default
transition: slide-left
---

## Displaying the 3D Secure Flow

1. Redirect to the bank website

- After confirmation, if a PaymentIntent has a `requires_action` status, inspect the PaymentIntent’s next_action. If it contains `redirect_to_url`, that means 3DS is required.

```
next_action: {
    type: 'redirect_to_url',
    redirect_to_url: {
      url: 'https://hooks.stripe.com/...',
      return_url: 'https://mysite.com'
    }
}
```

- In the browser, redirect the customer to the url in the `redirect_to_url` hash to complete authentication.

```
var action = intent.next_action;
  if (action && action.type === 'redirect_to_url') {
    window.location = action.redirect_to_url.url;
  }
```

When the customer finishes the authentication process, the redirect sends them back to the `return_url` you specified when you created or confirmed the PaymentIntent.