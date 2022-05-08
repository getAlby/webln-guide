# webln.enable()

To begin interacting with WebLN APIs you'll first need to enable the provider. Calling `webln.enable()` will prompt the user for permission to use the WebLN capabilities of the browser. After that you are free to call any of the other API methods.&#x20;

#### Method&#x20;

```typescript
async function enable(): void;
```

**Example**

```javascript
try {
  if(typeof window.webln !== 'undefined') {
    await window.webln.enable();
  }
}
catch(error) {
  // User denied permission or cancelled 
  console.log(error);
}
```

#### Demo

{% embed url="https://codepen.io/getalby/pen/YzYgYKE" %}
