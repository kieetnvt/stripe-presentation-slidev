---
layout: default
transition: slide-left
---

## Testing the 3D Secure flow

##### Test mode

```
| 4000000000003220 | Required  | The payment must complete 3DS2 authentication to be successful.

| 4000000000003063 | Required  | The payment must complete 3DS authentication to be successful.

| 4000008400001629 | Required  | 3DS authentication is required,
                                 but payments will be declined with a card_declined failure code after authentication.

| 4000000000003055 | Supported | 3DS authentication can still be performed, but isn’t required.

| 4242424242424242 | Supported | This card supports 3DS, but it isn’t enrolled in 3DS.
                                 This means that if your Radar rules request 3DS,
                                 the customer won’t go through additional authentication.
```