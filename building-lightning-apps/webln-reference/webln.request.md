---
description: >-
  A generic API to leverage the full potential of your connected node. Use any
  APIs your node provides.
---

# 🆕 webln.request()

➡️ This API is part of the [WebBTC](https://webbtc.dev/) spec

{% hint style="warning" %}
The available APIs heavily depend on the connector that is used. You can use [`webln.getInfo`](webln.getinfo.md) to check for supported methods. (`methods`)&#x20;
{% endhint %}

#### Method

```typescript
async function request(method: string, params: Object): RequestResponse;
```

#### Response

See the API docs of the connector that is currently in use.

#### Code Example <a href="#demo" id="demo"></a>

```typescript
await webln.enable();
await webln.request("listpeers");
```

#### Demos

* [Liquimercado ](https://replit.com/@getalby/liquimercado-core-lightning)(Core Lightning)
* [Liquimercado](https://replit.com/@getalby/liquimercado-lnd) (LND)
* [Boostagram viewer ](https://replit.com/@getalby/boostagram-viewer-LND#src/Home.tsx)(LND)

### Supported connectors

| Connector                                           | 🐝 Alby |
| --------------------------------------------------- | :-----: |
| [Core Lightning](https://lightning.readthedocs.io/) |    ✅    |
| [LND](https://api.lightning.community/)             |    ✅    |
