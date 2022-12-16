---
Description: >-
  What follows are suggestions on how best to integrate WebLN into your Bitcoin
  Lightning app. These aren't strict & hard rules, just ideas on how to prevent
  your user from being frustrated or overwhelm
---

# 🔆 Best Practices

### Inform & ask before you prompt

Most of WebLN's methods will prompt the user to make payments or have them provide information. Before running `window.webln.enable()` or other methods, make sure the user knows what your app does, and why they should allow your calls to run. Popping up a window as soon as they load a page will cause users to reject WebLN requests, or worse yet, bounce from your page. Explicit buttons (e.g. to login) are helpful, but alternatives could be hiding pages behind loaders while requesting the user's provider, or keeping it to sub-pages and having your homepage not require WebLN.

### Prioritize WebLN, offer fallback options

WebLN offers a very convenient way for users to interact with their lightning wallets. Therefore you should always check for WebLN support before showing some fallback options (QR codes, copy invoice, etc).

#### Code Example

```javascript
// check if the browser supports WebLN
if (window.webln) {
    try {
        // if webln is available, ask the user for permission (typically happens only once)
        await window.webln.enable();

        try {
            // if the user gave permission to use webln, initate the payment
            const res = await window.webln.sendPayment(parsed.invoice);
            // the response contains the pre-image of the payment and could be used to verify the payment by comparing the hashes
            console.log(res);
        }
        catch(e) {
            // something went wrong during the payment, inform the user
            showError(e);
        }

    }
    catch(e) {
        // if the user cancels or something goes wrong, we show the modal with the invoice and the QR code (as it is currently)
        showModal();
    }
} else {
    // if webln is not supported we simply show the modal as we currently do
    showModal();
}
```

If a user does not have a compatible client, inform them (e.g. with [Error](webln-reference/error-handling.md) messages) and let them know how to get started with a WebLN client. This is also a good time to promote your favorite WebLN provider projects!&#x20;

For simple use cases such as making payments, you can always just use BOLT-11 links instead of `webln.sendPayment` to have maximum compatibility with all types of Lightning clients.

```html
<a href="lightning:lnbc100...">Pay</a>
```

### **Don't Assume a Particular Client**

Anyone can make a WebLN provider, so don't assume the user is using a particular one, such as Alby or Joule. Try to stay agnostic in your language about the user's client, e.g. instead of saying `Pay`_`with Alby`_, just say `Pay`.
