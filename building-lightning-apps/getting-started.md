# 👨💻 👨💻 Getting Started

### Installation

Browsers with WebLN capabilities provide APIs using a global JavaScript variable `window.webln` that can be used to interact with the connected Bitcoin Lightning wallet.&#x20;

{% content-ref url="../ressources/webln-providers.md" %}
[webln-providers.md](../ressources/webln-providers.md)
{% endcontent-ref %}

**You don't need to add any library to your project.**

### Detecting WebLN support

Before you start using WebLN you need to check for browser support by checking if the variable `window.webln` is defined:

```javascript
if (typeof window.webln !== 'undefined') {
  console.log('WebLN is available!');
}
```

{% hint style="warning" %}
`window.webln` might not be available during pageload. See the code example below for proper detection.
{% endhint %}

<details>

<summary>Detect if a WebLN provider is available</summary>

```javascript
async function detectWebLNProvider(timeoutParam) {
  const timeout = timeoutParam ?? 3000;
  const interval = 100;
  let handled = false;

  return new Promise((resolve) => {
    if (window.webln) {
      handleWebLN();
    } else {
      document.addEventListener("webln:ready", handleWebLN, { once: true });
      
      let i = 0;
      const checkInterval = setInterval(function() {
        if (window.webln || i >= timeout/interval) {
          handleWebLN();
          clearInterval(checkInterval);
        }
        i++;
      }, interval);
    }

    function handleWebLN() {
      if (handled) {
        return;
      }
      handled = true;

      document.removeEventListener("webln:ready", handleWebLN);

      if (window.webln) {
        resolve(window.webln);
      } else {
        resolve(null);
      }
    }
  });
}
```

</details>

### Enable WebLN <a href="#connecting-to-metamask" id="connecting-to-metamask"></a>

Before you can work with any of the WebLN APIs you need call the method `enable()` :

```typescript
await window.webln.enable();
```

Depending on the used WebLN provider this will ask the user to connect their Lightning wallet with the website.&#x20;

![The WebLN provider will ask the user for permission to connect with your website.](<../.gitbook/assets/Group 4513.jpg>)

{% hint style="info" %}
You should only initiate a request in response to direct user action, such as clicking a button.
{% endhint %}

### Using WebLN

Now you are ready to work with the WebLN APIs.&#x20;

```javascript
await window.webln.enable();
await window.webln.sendPayment();
```

Have a look at the the [WebLN Reference](webln-reference/) for detailed explanations and usage examples for the different APIs.

### WebLN Events

WebLN triggers events like `webln:enabled` upon enabling, allowing apps and packages to subscribe and listen to these events.

```javascript
 window.addEventListener("webln:enabled", () => {
            console.log("WebLN is enabled!");
        });
```

### Error handling

There are different errors that can happen while using the WebLN APIs. Make sure to handle them and let the user know what went wrong.

{% content-ref url="webln-reference/error-handling.md" %}
[error-handling.md](webln-reference/error-handling.md)
{% endcontent-ref %}
