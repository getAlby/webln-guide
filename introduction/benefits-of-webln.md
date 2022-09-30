# 🏅 Benefits of WebLN

WebLN comes with a couple of benefits:

* **Better UX**\
  WebLN allows for programmatic interactions and reduces friction between a Lapp and user’s wallet. Users don't have to switch context for scanning a QR code to make a payment anymore. Additionally, they can sign a message with one click to prove ownership of a wallet. If a WebLN client supports auto-payments, no prompt is needed and the user is just one click away from sending a payment.
* **Ready and secure**\
  WebLN is a specification that only describes how to interact with a Bitcoin Lightning wallet. There is no need to trust and integrate a third party library. Over the years WebLN has developed and has been recognized as standard within the community.
* **Simple implementation**\
  Initialization and execution of WebLN requires not more than some lines of code of JavaScript - a language that is commonly used for creating web apps.
* **Complementary to LNURL**\
  WebLN works well together with [LNURL](https://github.com/fiatjaf/lnurl-rfc), another, more manual standard to make interactions with Lighting easier. If [implemented correctly](../building-lightning-apps/best-practices.md) WebLN provides a great enhancement of the UX. For users without a WebLN provider installed, LNURL can serve as a fall back option.
