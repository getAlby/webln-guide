# Error handling

There are different errors that could happen while using the WebLN APIs:

* User denies access to WebLN
* User cancels the process
* Connection errors
* Payment errors&#x20;

When an error happens during a WebLN API call the exception is thrown. Thus it is heavily recommended to handle different kinds of errors and let the user know what went wrong.&#x20;

```javascript
function pay() {
  if(typeof window.webln === 'undefined')
    return;
  
  try {
    await window.webln.enable();
    await window.webln.sendPayment(...);
  }
  catch(err) {
    console.log(error);
  }
}
```
