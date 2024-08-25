# Troubleshooting

## Troubleshooting Your gintonic Distillery Node

Even the smoothest-running machines hit a snag now and then. Don't worry - we've got you covered. This section will walk you through common issues and their solutions, helping you get back to earning $GIN in no time.

### Common Issues and Solutions

#### 1. Node Won't Start

**Symptoms**:

* Docker container won't run
* No logs being generated

**Possible Solutions**:

1.  Check if Docker is running:

    ```bash
    sudo systemctl status docker
    ```

    If it's not running, start it:

    ```bash
    sudo systemctl start docker
    ```
2.  Ensure you have the latest image:

    ```bash
    docker pull gintonic/distillery:latest
    ```
3.  Check your `gintonic-config.json` file for errors:

    ```bash
    cat ~/gintonic-config.json
    ```

    Make sure your wallet address is correct and the JSON is valid.

#### 2. Node is Online But Not Earning Rewards

**Symptoms**:

* Node shows as online in the monitor
* No rewards accumulating over 24+ hours

**Possible Solutions**:

1.  Check your GPU utilization:

    ```bash
    nvidia-smi
    ```

    If utilization is consistently low, your node might not be getting tasks.
2. Verify your wallet address in the config file matches the one you're checking rewards for.
3.  Ensure your node is fully synced with the network. Check logs for any sync issues:

    ```bash
    sudo cat /root/distillery_logs/script.log | grep "sync"
    ```

#### 3. High GPU Temperatures

**Symptoms**:

* GPU temperature consistently above 80°C
* Thermal throttling messages in logs

**Possible Solutions**:

1.  Reduce GPU allocation in your `gintonic-config.json`:

    ```json
    {
      "wallet_address": "YOUR_WALLET_ADDRESS",
      "gpu_allocation": 60  // Reduced from 70
    }
    ```
2. Improve cooling:
   * Clean dust from your GPU and case
   * Ensure good airflow around your machine
   * Consider additional cooling solutions if problem persists

#### 4. Network Connectivity Issues

**Symptoms**:

* Node frequently goes offline and online
* Logs show connection errors

**Possible Solutions**:

1. Check your internet connection stability
2. Ensure required ports are open (default is 14234). You may need to configure your router.
3. If using a VPN, try disabling it to see if it resolves the issue.

### Error Messages Explained

Here are some common error messages you might see in your logs, and what they mean:

* `ERROR: Failed to connect to initial peer`: Your node can't reach our network entry point. Check your internet connection and firewall settings.
* `WARN: High memory usage detected`: Your GPU is running out of VRAM. Consider lowering your GPU allocation.
* `ERROR: Invalid configuration`: There's an issue with your `gintonic-config.json` file. Double-check its contents.
* `WARN: Task execution timed out`: A task took too long to complete. This occasionally happens and isn't a cause for concern unless frequent.

### When to Seek Help

If you've tried the solutions above and are still having issues, it's time to reach out. Here's where to get help:

1. **Community Forum**: Post your issue on our [gintonic Community Forum](https://community.gintonic.ai). Many experienced node operators hang out here and can offer advice.
2. **Discord Channel**: Join our [Discord](https://discord.gg/gintonic) and post in the #node-help channel. Our team and community members actively monitor this.
3. **Email Support**: For sensitive issues or if other channels haven't helped, email us at support@gintonic.ai.

When seeking help, always provide:

* Your node's Peer ID
* Relevant log entries
* Steps you've already tried

Remember, everyone was new once. Don't hesitate to ask for help - our community is here to support you!

Running a node is a learning process. Each issue you solve makes you more knowledgeable and your node more reliable. Keep at it! \{% endhint }

In the next section, we'll cover a glossary of terms to help you navigate the gintonic ecosystem like a pro. Happy troubleshooting!
