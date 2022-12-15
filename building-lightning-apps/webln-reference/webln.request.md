---
description: >-
  A generic API to leverage the full potential of your connected node. Use any
  API node provides.
---

# 🆕 webln.request()

➡️ This API is part of the upcoming [WebBTC](https://webbtc.dev/) spec.&#x20;

{% hint style="warning" %}
The available APIs heavily depend on the connector that is used. You can use [`webln.getInfo`](webln.getinfo.md) to check for supported methods. (`methods`)&#x20;
{% endhint %}

#### Method

```typescript
async function request(method: string, params: Object): RequestResponse;
```

#### Response

See the API docs of the connector that is currently in use. (e.g. the [LND API](https://api.lightning.community/) or the [CLN API](https://lightning.readthedocs.io/))

#### Code Example (using LND) <a href="#demo" id="demo"></a>

<pre class="language-typescript"><code class="lang-typescript">await webln.enable();

// check if the connected node supports the required methods
<strong>const info = await webln.getInfo();
</strong><strong>if (!info.methods.includes("listpeers")) {
</strong><strong>  alert('Invalid node connection. Please use LND');
</strong><strong>}
</strong>// list all connected peers
await webln.request("listpeers");
// response: 
{ peers: [
  address: "85.128.153.40:9735",
  bytes_recv: "23275891"
  bytes_sent: "519238"
  ... see LND API: https://api.lightning.community/#lnrpc-peer
]}

// connect to a new peer
const pubkey = "02af02be7c7e5cf...";
const host = "152.82.72.42:9735";
await webln.request('connectpeer', { addr: {host, pubkey }, perm: true})
</code></pre>

#### Demos

* [Liquimercado ](https://replit.com/@getalby/liquimercado-core-lightning)(Core Lightning)
* [Liquimercado](https://replit.com/@getalby/liquimercado-lnd) (LND)
* [Boostagram viewer ](https://replit.com/@getalby/boostagram-viewer-LND#src/Home.tsx)(LND)

### Supported connectors

| Connector                                           | 🐝 Alby |
| --------------------------------------------------- | :-----: |
| [Core Lightning](https://lightning.readthedocs.io/) |    ✅    |
| [LND](https://api.lightning.community/)             |    ✅    |
