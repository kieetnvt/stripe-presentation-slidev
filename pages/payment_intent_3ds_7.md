---
layout: default
transition: slide-left
---

## Displaying the 3D Secure Flow

2. Display in an iframe

- Made PaymentIntent Confirm with `return_url`

- Check PaymentIntent status, if `requires_action` status, An additional step like 3D Secure is required

- Render iframe

```
var iframe = document.createElement('iframe');
  iframe.src = paymentIntent.next_action.redirect_to_url.url;
  iframe.width = 600;
  iframe.height = 400;
  yourContainer.appendChild(iframe);
```

- The iframe redirects to the return_url you provided when confirming the PaymentIntent.

- On `return_url`, retrieve the updated PaymentIntent and check on the status of the payment.