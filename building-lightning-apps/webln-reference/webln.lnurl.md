# 🆕 webln.lnurl()

Request to execute a [LNURL](https://github.com/lnurl/luds) request. The application needs to pass a [LNURL](https://github.com/lnurl/luds/blob/luds/01.md) string which should be provided for example by the application's backend. The lnurl function can also accept a [LUD-16](https://github.com/lnurl/luds/blob/luds/16.md) static identifier (e.g. username@getalby.com) instead of a LNURL string.

The method returns a promise which resolves once the LNURL flow is completed. It returns the last response from the LNURL server. For LNURL-pay requests it also contains payment information (preimage, payment hash) and for LNURL-auth requests it contains auth information (message, signature)&#x20;

{% hint style="warning" %}
This API may not be available on all [providers](https://www.webln.guide/ressources/webln-providers).&#x20;
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
      data?: unknown
    }
  | { status: "ERROR"; reason: string };
```

#### LNURL-pay Response&#x20;

```typescript
type LNURLPayResponse =
  | {
      status: "OK";
      data: { 
        preimage: string, 
        paymentHash: string, 
        paymentRequest: string
      }
    }
  | { status: "ERROR"; reason: string };
```

#### LNURL-auth Response&#x20;

```typescript
type LNURLAuthResponse =
  | {
      status: "OK";
      data: { 
        message: string, 
        signature: string
      }
    }
  | { status: "ERROR"; reason: string };
```

#### Code Example <a href="#demo" id="demo"></a>

```typescript
// const lnurl = (provided by your application backend)
if (!webln.lnurl) { alert('not supported'); }

await webln.enable();
const result = await webln.lnurl(lnurl); // promise resolves once the LNURL process is finished (e.g. a payment is sent or the login is complete)
```

#### Demos

* [Lightsats](http://lightsats.com/) (LNURL-pay, LNURL-withdraw)
* [getAlby.com](https://getalby.com/) (LNURL-auth login via getAlby extension, Lightning address)
