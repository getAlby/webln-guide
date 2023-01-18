# 🆕 webln.lnurl()

Request that the user executes a [LNURL](https://github.com/lnurl/luds) request. The application needs to provide a [LNURL](https://github.com/lnurl/luds/blob/luds/01.md) string which should be provided by the application's backend.

{% hint style="warning" %}
This API may not be available on all [providers](https://www.webln.guide/ressources/webln-providers).
{% endhint %}

#### Method

```typescript
async function lnurl(lnurl: string): LNURLResponse;
```

#### Response

```typescript
type LNURLResponse =
  | {
      status: "OK";
    }
  | { status: "ERROR"; reason: string };
```

#### Code Example <a href="#demo" id="demo"></a>

```typescript
// const lnurl = (provided by your application backend)
await webln.enable();
const result = await webln.lnurl(lnurl);
```

#### Demos

* [Lightsats](http://lightsats.com/) (LNURL-pay, LNURL-withdraw)
* [getAlby.com](https://getalby.com/) (LNURL-auth login via getAlby extension, Lightning address)
