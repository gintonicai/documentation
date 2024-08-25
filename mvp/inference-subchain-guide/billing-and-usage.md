---
description: >-
  Understand the billing model and track your usage of the gintonic Inference
  Subchain. Learn about pricing, monitoring costs, and managing your account.
---

# Billing and Usage

## Billing and Usage

Let's talk money. We know you're here for the AI magic, but understanding how billing works is crucial to keep your projects running smoothly. Don't worry, we've made it as painless as possible.

### Pay-as-You-Go Model

We're all about flexibility here at gintonic. Our pay-as-you-go model means you only pay for what you use. No hefty upfront costs or monthly commitments. Here's how it works:

1. **Deposit $GIN**: Top up your account with $GIN.
2. **Use the Service**: Make API calls to your heart's content.
3. **Automatic Deduction**: We deduct $GIN based on your usage.

Simple, right? Now, let's break it down further.

### Token Economics

In the world of gintonic, $GIN are your currency. Here's what you need to know:

* **1 $GIN Token** = 1,000,000AI tokens
* **AI Tokens**: These are the units used to measure the length of input and output text.
* **Pricing**: Check our pricing page for the most up-to-date rates.

Pro Tip: Keep an eye on your token usage to estimate costs. A typical conversation turn uses about 500-1500 AI tokens.

#### Depositing Funds

To deposit funds, call the 'deposit' endpoint of the $GIN token smart contract. This process allows you to add $GIN to your account balance.

### Viewing Your Balance

Staying on top of your balance is easy:

1. Log into your [gintonic inference Console](https://console.gintonic.ai/inference)
2. Navigate to the 'Billing' section
3. You'll see your current balance prominently displayed

You can also check your balance programmatically:

```python
from gintonic import InferenceClient

client = InferenceClient(api_key="your_api_key_here")
balance = client.get_balance()
print(f"Current balance: {balance} $GIN")
```

### Managing Your Balance

#### Topping Up

Running low? No problem. Here's how to add funds:

1. Go to the 'Billing' section in your gintonic Console
2. Click on 'Top Up Balance'
3. Choose the amount you want to add
4. Complete the transaction using MetaMask

Remember, $GIN are blockchain-based. Make sure you have enough ETH in your wallet to cover gas fees!

#### Auto-Recharge

Never want to run out of tokens? Set up auto-recharge:

1. In the 'Billing' section, find 'Auto-Recharge Settings'
2. Set your preferred threshold and recharge amount
3. Save your settings

Now your account will automatically top up when it hits the threshold. Magic!

#### Depositing Funds

To deposit funds, call the 'deposit' endpoint of the $GIN token smart contract. This process allows you to add $GIN to your account balance.

### Understanding Your Usage

Knowledge is power, especially when it comes to managing costs. Here's how to dive into your usage details:

1. In the gintonic Console, go to 'Usage Analytics'
2. You'll see graphs showing your token usage over time
3. Use the date range selector to zoom in on specific periods

### Notifications and Balance Thresholds

We've got your back when it comes to keeping track of your balance. Here's how our notification system works:

| Balance Threshold | What Happens               | Notification                                                                                        |
| ----------------- | -------------------------- | --------------------------------------------------------------------------------------------------- |
| 30% remaining     | Normal operation continues | "You have less than Y tokens left. Consider topping up your deposit."                               |
| 10% remaining     | Normal operation continues | "You have less than X tokens left. Consider topping up your deposit."                               |
| 0% (Depleted)     | Service paused             | "Token balance is depleted. Interaction with the model is paused. You have to top up your deposit." |

When your balance hits 0:

* You can't send new messages into the dialog
* The 'save & apply', 'create & apply', and 'load' buttons are deactivated

Don't worry, though. As soon as you top up, everything will be back to normal!

### Billing FAQ

**Q: Can I get a refund for unused tokens?** A: Not at the moment. Tokens don't expire, though, so save them for your next project!

**Q: Is there a way to set a spending limit?** A: Absolutely! In the 'Billing' section, you can set a maximum monthly spend limit.

**Q: Do you offer volume discounts?** A: For high-volume users, we offer custom pricing. Contact our sales team for more info.

**Q: How often is my usage calculated?** A: We calculate usage in real-time, but for performance reasons, your visible balance is updated every few minutes.

Remember, transparent and predictable billing is part of our mission to make AI accessible. If you ever have questions about your bill or usage, don't hesitate to reach out to our support team.

Now that you're a billing pro, go forth and create amazing AI-powered applications without breaking the bank!
