# 🆕 webln.isEnabled()

`webln.isEnabled()` allows you to check if webln is enabled without explicitly enabling it through `webln.enable()` (which may cause a confirmation popup in some providers)

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
