# Managing Your Node

## Managing Your Gintonic Distillery Node

Now that your node is up and running, earning you $GIN, it's important to keep an eye on its performance and health. This section will show you how to monitor your node, understand its status, and perform basic maintenance tasks.

### Checking Node Status

Want to see how your node is doing? It's easy:

1. Visit our [Node Monitor Page](https://petals-monitor.sfxdx.com/)
2. Find your node using your wallet address or Peer ID

Here's what you'll see:

* **Status**: Online/Offline
* **Uptime**: How long your node has been running
* **Tasks Completed**: Number of tasks your node has processed
* **Current Load**: How hard your GPU is working right now

{% hint style="info" %}
The monitor page updates every few minutes. If you've just started your node, it might take a little while to show up.
{% endhint %}

### Accessing and Understanding Logs

Logs are like your node's diary - they record everything that happens. Here's how to read them:

1. Open a terminal on your machine
2.  Run this command:

    ```bash
    sudo cat /root/distillery_logs/script.log
    ```

You'll see entries like:

```
[2024-08-24 15:30:22] INFO: Node started successfully
[2024-08-24 15:35:10] INFO: Completed task XYZ123, processed 1000 blocks
[2024-08-24 15:40:05] WARN: High GPU temperature detected
```

Don't worry about understanding every line. Look out for:

* `INFO`: Normal operations
* `WARN`: Potential issues to keep an eye on
* `ERROR`: Problems that need your attention

### Starting and Stopping Your Node

Need to take your node offline for a bit? No problem:

To stop your node:

```bash
docker stop gintonic-distillery
```

To start it back up:

```bash
docker start gintonic-distillery
```

{% hint style="warning" %}
Remember, your node only earns $GIN when it's online and processing tasks. Try to minimize downtime!
{% endhint %}

Your Gintonic client can be stopped in several ways:

- Using the docker stop command (as shown above)
- Manually killing the process
- Restarting or shutting down your machine
- Using the CTRL+C keyboard shortcut if running in an interactive terminal

Regardless of how it's stopped, you can always restart your node using the docker start command provided earlier.

### Updating Your Node

We're constantly improving Gintonic. To get the latest version:

1.  Stop your node:

    ```bash
    docker stop gintonic-distillery
    ```
2.  Remove the old container:

    ```bash
    docker rm gintonic-distillery
    ```
3.  Pull the latest image:

    ```bash
    docker pull gintonic/distillery:latest
    ```
4.  Start a new container:

    ```bash
    docker run -d --gpus all -v ~/gintonic-config.json:/app/config.json --name gintonic-distillery gintonic/distillery:latest
    ```

### Monitoring GPU Health

Your GPU is the workhorse of your node. Keep it healthy:

1.  Install GPU monitoring tools:

    ```bash
    sudo apt install nvidia-smi
    ```
2.  Check GPU status:

    ```bash
    nvidia-smi
    ```

Watch out for:

* High temperatures (over 80°C)
* Memory errors
* Power fluctuations

If you notice any issues, consider adjusting your GPU allocation in the `gintonic-config.json` file.

### Best Practices

* **Regular Check-ins**: Look at your node status daily
* **Update Regularly**: Check for updates weekly
* **Cool and Clean**: Ensure good ventilation for your GPU
* **Stable Power**: Use a UPS if possible to prevent sudden shutdowns

By keeping your node healthy and up-to-date, you're not just maximizing your $GIN earnings - you're ensuring the Gintonic network stays robust and efficient.

In the next section, we'll cover common troubleshooting steps to help you solve any issues that might pop up. Keep distilling!
