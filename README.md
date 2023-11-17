# 👋 Welcome

Welcome to the Lightning Web Standard (WebLN). 
This guide covers how to build a Bitcoin Lightning-driven web application using the WebLN standard.

Bitcoin is a global payment protocol that anyone with Internet access can participate in and contribute to. Hence, Bitcoin Lightning’s use cases are as vast as its user base. However, building them does not need to be complicated. We designed this guide to help anyone get started quickly. We can’t imagine every possible use case, but we can help you to build for them.

You may be interested in reading this guide if you want to build or operate a web application

* that accepts or makes Bitcoin Lightning payments
* that have decentralized identity and authentication

All you need is to interact with a client application such as a browser extension that understands WebLN. It does so by providing a JavaScript API called `window.webln` on every web page you visit. To have a look at what this object looks like, have a look at the [WebLN Reference](building-lightning-apps/webln-reference/) or just type `window.webln` in the Chrome or Firefox DevTools console.

WebLN is a JavaScript interface to the Bitcoin Lightning Network. There are functions to:

* Get information about a user's Bitcoin Lightning node ([`webln.getInfo`](building-lightning-apps/webln-reference/))
* Send a payment ([`webln.sendPayment`](building-lightning-apps/webln-reference/))
* Request an invoice to receive a payment ([`webln.makeInvoice`](building-lightning-apps/webln-reference/))
* Request a signature of an arbitrary message ([`webln.signMessage`](building-lightning-apps/webln-reference/))
* …and [some more](building-lightning-apps/webln-reference/)

When a WebLN provider is installed, any front-end code can get access to all these functions, and interact with the Bitcoin Lightning network. These web applications are called _LApps_ (Lightning Apps).
