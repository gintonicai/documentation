---
description: >-
  In this section you will know gow to manage your account and monitor billing
  information on our platform.
---

# Billing and Usage

### Account Overview

Navigate to the Account page to access the following features:

* View your current balance
* Top up your balance
* View and generate API keys
* Fine-tune AI model

### Billing Model

Gintonic uses a pay-as-you-go model. This means that you deposit funds onto the platform and can use our services freely until your deposit is depleted. Each API call deducts GIN tokens from your balance.

To deposit funds, call the 'deposit' endpoint of the GIN token smart contract.

### View Usage

To view detailed usage and billing information, log into the platform and check the 'Billing' section.

Deposit is performed by calling ‘deposit’ endpoint of GIN token smart contract.

### Top Up Balance

To top up your balance, use Metamask to add funds to your account directly from the 'Billing' section.

### Get notification&#x20;

You can receive notifications at certain stages of deposit depletion to ensure that you never run out of funds.

| Tokens balance | Effects on user operation                                                                                                                                                                         | Notification                                                                                                        |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| 30%            | none, give notification                                                                                                                                                                           | “You have less than Y tokens left. Consider to \[top up your deposit]\(accountURL).”                                |
| 10%            | none, give notification                                                                                                                                                                           | “You have less than X tokens left. Consider to \[top up your deposit]\(accountURL).”                                |
| 0%             | <ul><li>user can not send new messages into the dialog,</li><li>buttons ‘<em>save&#x26;apply/create&#x26;apply</em>’ and ‘<em>load</em>’ are deactivated,</li><li>notification is given</li></ul> | “Token balance is depleted. Interaction with the model is paused. You have to \[top up your deposit]\(accountURL).” |
