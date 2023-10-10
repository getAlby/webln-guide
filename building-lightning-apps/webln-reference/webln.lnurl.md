# 🆕 webln.sendPaymentAsync()

Request that the user sends a payment for an invoice. The application needs to provide a [BOLT-11](https://github.com/lightningnetwork/lightning-rfc/blob/master/11-payment-encoding.md) invoice. The payment will only be initiated and will not wait for a preimage to be returned. This is useful when paying [HOLD invoices](https://guides.getalby.com/alby-guides/alby-browser-extension/features/hold-payments). There is no guarantee that the payment will be successfully sent to the receiver. It's up to the receiver to check whether or not the invoice has been paid.

{% hint style="warning" %}
This API may not be available on all [providers](https://www.webln.guide/ressources/webln-providers).&#x20;
{% endhint %}

**Method**

```typescript
async function
    sendPaymentAsync(paymentRequest: string): SendPaymentAsyncResponse;
```

#### Parameters

```javascript
paymentRequest: string // the invoice you'd like the user to pay (lnbc...)
```

#### Response

```typescript
interface SendPaymentAsyncResponse {} // no preimage returned!
```

#### Example

```typescript
const invoice = "lnbc100...";
const result = await window.webln.sendPaymentAsync(invoice);
```

#### Demo

{% embed url="https://codepen.io/getalby/pen/KKbJvWy" %}
