# webln.getInfo()

Get information about the connected node: node alias, public key and color

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
  // Not supported by all connectors (see webln.request for more info)
  methods: string[]; 
}
```

#### Code Example

```typescript
await webln.enable();
const info = await webln.getInfo();
```

#### Demo

{% embed url="https://codepen.io/getalby/pen/VwyREdo" %}
