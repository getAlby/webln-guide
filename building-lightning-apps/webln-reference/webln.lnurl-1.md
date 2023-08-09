# 🆕 webln.on()

This method specifically allows you to listen for a particular event such as "accountChanged" and execute a callback function when this event occurs.

{% hint style="warning" %}
This API may not be available on all [providers](https://www.webln.guide/ressources/webln-providers).&#x20;
{% endhint %}

#### Method

```typescript
function on(eventName: "accountChanged", listener: () => void): void;
```

#### Code Example <a href="#demo" id="demo"></a>

```typescript
if (!webln.on) { alert('not supported'); }

await webln.enable();
webln.on("accountChanged", () => {console.log("account Changed!")}); // callback is executed once account is changed in provided with multiple accounts
```

#### Demo

{% embed url="https://codepen.io/getalby/pen/Rwqmodm" %}
