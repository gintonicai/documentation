---
description: >-
  Learn how rewards are calculated and distributed in the gintonic Distillery
  network. Discover strategies to maximize your earnings and withdraw rewards.
---

# Earning Rewards

## Earning Rewards on the gintonic Network

You've set up your node, joined the network, and now your GPU is humming away, contributing to AI tasks. But how exactly do you earn those sweet $GIN? Let's break it down.

### How Rewards are Calculated

Earning $GIN isn't about luck or solving random puzzles. It's directly tied to the work your GPU does. Here's a simplified look at how it works:

1. **Job Assignment**: The network receives AI processing jobs and divides them into smaller tasks.
2. **Work Distribution**: Your node gets a piece of the action based on its availability and capabilities.
3. **Computation**: Your GPU crunches the numbers, doing its part in the larger AI task.
4. **Contribution Measurement**: The network tracks how much of the task your node completed.
5. **Reward Calculation**: Your reward is calculated based on your contribution to the overall job.

The exact formula looks like this:

```
Reward = (Job_Price - System_Fee) * (Your_Blocks / Total_Job_Blocks)
```

Where:

* `Job_Price` is currently set at 1 $GIN per message processed
* `System_Fee` is a small 0.1% fee (0.001 $GIN) for network maintenance
* `Your_Blocks` is the number of blocks your GPU processed
* `Total_Job_Blocks` is the total size of the job

Don't worry if this seems complex - your node handles all the tracking automatically!

On the backend, here's how the charging process works:

1. When an inference job is initiated, the system calculates the charge per message.
2. This charge is added to the system balance (no actual token transfers occur at this stage).
3. As nodes (including yours) complete work, rewards are distributed from this system balance.

This process ensures fair and transparent distribution of rewards based on the actual work completed by each node.

## Technical Details of Reward Distribution

For transparency, here's how rewards are distributed at a system level:

* If your node is the initial peer, rewards go to a special initial\_peer\_public\_address.
* If your node has a registered public address, rewards go directly to that address.
* If your node doesn't have a registered public address, rewards go to an unauth\_peer\_public\_address.

The system also maintains a system\_public\_address that receives system fees and rewards for unauthorized peers.

{% hint style="info" %}
These addresses are managed by the gintonic system. As a node operator, you only need to ensure your node is properly set up with your public address.
{% endhint %}

### Checking Your Reward Balance

Curious about how much you've earned? Here's how to check:

1. Visit the [gintonic Rewards Dashboard](https://rewards.gintonic.ai) (replace with actual URL)
2. Connect your wallet (the same one you used to set up your node)
3. You'll see your current $GIN balance and a history of your earnings

{% hint style="info" %}
The dashboard updates every 15 minutes. If you've just started, give it some time to show your earnings.
{% endhint %}

### Withdrawing Your Rewards

Ready to claim your $GIN? Follow these steps:

1. On the Rewards Dashboard, click the "Withdraw" button
2. Choose how much $GIN you want to withdraw
3. Confirm the transaction in your wallet (e.g., MetaMask)
4. Wait for the transaction to process (usually takes a few minutes)

And voila! The $GIN will be sent to your connected wallet address.

{% hint style="warning" %}
Remember, blockchain transactions incur small fees. Make sure you're withdrawing enough to make it worthwhile!
{% endhint %}

### Maximizing Your Rewards

Want to earn more $GIN? Here are some tips:

* **Keep your node online**: The more your GPU is available, the more tasks it can complete.
* **Upgrade your hardware**: Better GPUs can handle more complex tasks, potentially earning more.
* **Optimize your setup**: Ensure your system is running efficiently to handle more tasks.

Remember, earning rewards with gintonic isn't just about making money - you're contributing to the advancement of AI technology. Every task your GPU completes helps researchers and developers push the boundaries of what's possible with AI.

In the next section, we'll cover how to manage and monitor your node to keep it running smoothly. Happy earning!
