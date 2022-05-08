# webln.verifyMessage()

Opens an external view where the user's client verifies the signature against the raw message, and let's the user know if it was valid. There's no return value, this method is intended purely for the user to verify a signature themselves without having to trust your website.

#### Method

```typescript
function verifyMessage(signature: string, message: string): void;
```

#### Code example <a href="#demo" id="demo"></a>

```typescript
await webln.enable();
await webln.verifyMessage("rbpr1...", "Message"); 
```

#### Demo

{% embed url="https://codepen.io/getalby/pen/vYpPQLG" %}
