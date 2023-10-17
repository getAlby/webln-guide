# 🆕 webln.isEnabled()

`webln.isEnabled()`checks if the WebLN has ever been enabled during the user's session and remains enabled without being explicitly disabled. If it returns `true`, it means that WebLN functionality has been granted and remains accessible, allowing developers to adapt their applications accordingly for a more seamless user experience.



{% hint style="warning" %}
This API may not be available on all [providers](https://www.webln.guide/ressources/webln-providers).&#x20;
{% endhint %}

#### Method&#x20;

```typescript
function isEnabled(): Promise<boolean>;
```

**Example**

```javascript
 if(typeof window.webln !== 'undefined' && window.webln.isEnabled) {
    const isEnabled = await window.webln.isEnabled();
    // do something with the value
    console.log(isEnabled)
  }
```

#### Demo

{% embed url="https://codepen.io/getalby/pen/vYvqZgy" %}
