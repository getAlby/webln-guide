# 🆕 webln.getBalance()

Fetch the balance of the current account.

{% hint style="warning" %}
This API may not be available on all [providers](https://www.webln.guide/ressources/webln-providers).&#x20;
{% endhint %}

#### Method

```typescript
async function getBalance(): BalanceResponse;
```

#### Response

```typescript
type BalanceResponse = {
    balance: number;
    currency?: "sats" | "EUR" | "USD"
}
```

**Code Example**

```typescript
await webln.enable();
const result = await webln.getBalance();
```

**Demo**

{% embed url="https://codepen.io/getalby/pen/xxQabJx" %}

