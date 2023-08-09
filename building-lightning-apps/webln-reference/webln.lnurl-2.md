# 🆕 webln.off()

This particular method enables you to cancel your subscription to an event that was initially set up using the `webln.on()` function. This allows you to stop receiving notifications or triggers when a specific event occurs.

{% hint style="warning" %}
This API may not be available on all [providers](https://www.webln.guide/ressources/webln-providers).&#x20;
{% endhint %}

#### Method

```typescript
function off(eventName: "accountChanged", listener: () => void): void;
```

#### Code Example <a href="#demo" id="demo"></a>

```typescript
if (!webln.on) { alert('not supported'); }

await webln.enable();
// subscribe to the accountChanged event
webln.on("accountChanged", accountChangedHandler); // callback is executed once account is changed in provided with multiple accounts

// use .off() to unsubscribe from the event. 
webln.off("accountChanged", accountChangedHandler);

function accountChangedHandler(){
console.log("Account Changed!");
}


```

