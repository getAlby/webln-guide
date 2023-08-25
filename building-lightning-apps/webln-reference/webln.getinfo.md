# webln.getInfo()

Get information about the connected node and what WebLN methods it supports.

#### Method

```typescript
async function getInfo(): GetInfoResponse;
```

#### Response

```typescript
interface GetInfoResponse = {
  node: {
    alias: string;
    pubkey: string;
    color?: string;
  },
  // "request.*" methods are not supported by all connectors
  // (see webln.request for more info)
  methods: string[]; // e.g. "makeInvoice", "sendPayment", "request.openchannel", ...
}
```

#### Code Example

```typescript
await webln.enable();
const info = await webln.getInfo();
```

#### Demo

{% embed url="https://codepen.io/getalby/pen/VwyREdo" %}
