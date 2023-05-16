# webln.sendPayment()

Request that the user sends a payment for an invoice. The application needs to provide a [BOLT-11](https://github.com/lightningnetwork/lightning-rfc/blob/master/11-payment-encoding.md) invoice. For an invoiceless payment, use [webln.keysend](broken-reference).

**Method**

```typescript
async function sendPayment(paymentRequest: string): Promise<SendPaymentResponse>;
```

#### Parameters

```typescript
async function sendPayment(paymentRequest: string): Promise<SendPaymentResponse>;
```

#### Response

```typescript
interface SendPaymentResponse {
  preimage: string;
}
```

#### Example

```typescript
const invoice = "lnbc100...";
const result = await window.webln.sendPayment(invoice);
```

#### Demo

{% embed url="https://codepen.io/getalby/pen/RwxdQNO" %}
