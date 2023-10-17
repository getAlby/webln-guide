# webln.enable()

To begin interacting with WebLN APIs you'll first need to enable the provider. Calling `webln.enable()` will prompt the user for permission to use the WebLN capabilities of the browser. After that you are free to call any of the other API methods.&#x20;

#### Method&#x20;

```typescript
async function enable(): void;
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

{% embed url="https://codepen.io/getalby/pen/YzYgYKE" %}
