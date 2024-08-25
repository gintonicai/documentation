# Joining the Network

## Joining the Compute Mining Network

Congratulations on setting up your gintonic Distillery node! Now it's time to connect to the network and start earning those $GIN tokens. This section will walk you through the process of joining the compute mining network and explain some key concepts along the way.

### Providing Your Public Address

Remember that wallet address you set up in the previous section? That's your ticket to getting paid. Here's why it's important:

* It's where your $GIN rewards will be sent
* It uniquely identifies you on the network
* It helps us track your contributions accurately

{% hint style="danger" %}
**Never share your private key!** Your public address is safe to share, but keep your private key secret. Anyone with your private key can access your funds.
{% endhint %}

### Connecting to the Network

Good news! If you followed the steps in the "Getting Started" section, your node is already trying to connect to the network. Here's what's happening behind the scenes:

1. Your node reaches out to our initial peer (think of it as a network doorman)
2. The initial peer helps your node find other peers to work with
3. Your node joins the swarm of other GPUs, ready to take on tasks

This process is automatic, so you don't need to do anything extra. Pretty cool, right?

{% hint style="warning" %}
Note: The 'initial\_peer' address is provided during the installation process. This is currently a security risk that will be addressed in future releases.
{% endhint %}

## Technical Details of Network Connection

When your node joins the network:

* It connects to an 'initial\_peer' address. This address is provided during the installation process.
* By default, your node allocates 70% of your GPU's capacity to gintonic tasks. You can adjust this in your configuration file if needed.

{% hint style="warning" %}
The 'initial\_peer' address is crucial for network security. Never share this address or try to alter it manually.
{% endhint %}

### Understanding Peer IDs and Addresses

In the world of decentralized networks, identities work a bit differently. Let's break it down:

* **Peer ID**: This is a unique identifier for your node on the network. It's automatically generated when you start your node and looks something like `QmYyQSo1c1Ym7orWxLYvCrM2EmxFTANf8wXmmE7DWjhx5N`.
* **Public Address**: This is your wallet address that you provided earlier. It's linked to your Peer ID in our system.

Here's why this matters:

1. The network uses your Peer ID to assign tasks and track your node's performance
2. We use your Public Address to know where to send your hard-earned $GIN tokens
3. This two-part identity helps keep the network secure and your rewards safe

{% hint style="info" %}
You don't need to memorize or manage your Peer ID. Your node handles this automatically. Just remember your Public Address - that's where the good stuff ($GIN) goes!
{% endhint %}

### Checking Your Connection

Want to make sure everything's running smoothly? Here's how to check:

1. Open a terminal on your machine
2.  Run this command:

    ```bash
    docker logs gintonic-distillery
    ```
3. Look for a message like "Successfully joined the gintonic network"

If you see that message, congratulations! Your GPU is now part of the gintonic swarm, ready to take on AI tasks and earn you some $GIN.

In the next section, we'll cover how rewards are calculated and how to check your earnings. Get ready to watch those $GIN tokens roll in!
