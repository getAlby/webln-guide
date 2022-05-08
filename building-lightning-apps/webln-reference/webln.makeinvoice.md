# webln.makeInvoice()

Request that the user creates an invoice to be used by the web app. This will return a [BOLT-11](https://github.com/lightningnetwork/lightning-rfc/blob/master/11-payment-encoding.md) invoice. Invoices can be requested in a few forms:

* By specifying an explicit `amount`, the user's provider should enforce that the user generate an invoice with a specific amount
* By specifying a `minimumAmount` and / or `maximumAmount`, the user's provider should enforce that the user generate an invoice with an amount field constrained by that amount
* When an explicit `amount` is _not_ set, the user can return an invoice that has no amount specified, allowing the payment maker to send any amount

Note that these constraints are enforced by the client's provider, and therefore should not be completely trusted. If you want to check the fields that come back, or otherwise use the data encoded in the invoice, you'll want to use a library to decode it such as the [bolt11 npm package](https://www.npmjs.com/package/bolt11).

Amounts are denominated in satoshis. For large amounts, it's recommended you use a big number library such as [bn.js](https://www.npmjs.com/package/bn.js) as Javascript only supports 32 bit integers.

#### Method

```typescript
async function makeInvoice(args: RequestInvoiceArgs): RequestInvoiceResponse;
```

#### Parameters

```typescript
interface RequestInvoiceArgs {
  amount?: string | number;
  defaultAmount?: string | number;
  minimumAmount?: string | number;
  maximumAmount?: string | number;
  defaultMemo?: string;
}
```

{% hint style="info" %}
All amounts are denominated in sats.
{% endhint %}

#### Response

```typescript
interface RequestInvoiceResponse {
  paymentRequest: string;
}
```

#### Code Example

```typescript
await webln.enable();
const invoice = await webln.makeInvoice({ 
    amount: 1000,
});
```

#### Demo

{% embed url="https://codepen.io/getalby/embed/mdpozoV?default-tab=js%2Cresult&theme-id=light" %}
