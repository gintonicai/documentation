# Getting Started

## Getting Started with gintonic Distillery

Ready to put your GPU to work? Great! This guide will walk you through the process of joining the gintonic Distillery network. Don't worry if you're not a tech wizard - we've designed this process to be as straightforward as possible.

### System Requirements

Before we dive in, let's make sure your system is up to the task:

* **GPU**: NVIDIA GPU with at least 8GB of VRAM
* **Operating System**: Ubuntu 20.04 LTS or later
* **Storage**: At least 50GB of free disk space
* **Internet**: Stable broadband connection

{% hint style="warning" %}
While it's possible to run on other setups, we've optimized for these specifications. Your mileage may vary with different configurations.
{% endhint %}

### Installation Guide

1.  **Update your system**

    Open a terminal and run:

    ```bash
    sudo apt update && sudo apt upgrade -y
    ```
2.  **Install NVIDIA drivers**

    If you haven't already, install the latest NVIDIA drivers:

    <pre class="language-bash"><code class="lang-bash"><strong># You'll also need python3.9 or higher, and the nvidia-smi package
    </strong>sudo apt install python3.9 nvidia-smi
    sudo ubuntu-drivers autoinstall
    sudo reboot
    </code></pre>
3.  **Install Docker**

    We use Docker to keep things neat and tidy. Install it with:

    ```bash
    curl -fsSL https://get.docker.com -o get-docker.sh
    sudo sh get-docker.sh
    ```
4.  **Pull the gintonic Distillery image**

    Grab our Docker image:

    ```bash
    ```bash
docker pull gintonic/distillery:latest
    ```
5.  **Set up your wallet**

    You'll need an Ethereum-compatible wallet to receive your $GIN. \
    If you don't have one, we recommend [MetaMask](https://metamask.io/). Make sure to keep your private keys safe and secure!
6. **You'll also need to:**
   1. Create an account on [HuggingFace](https://huggingface.co/)
   2. Create an Access Token in your HuggingFace account settings
   3. Confirm access to this repository: [Mixtral-8x7B-Instruct-v0.1](https://huggingface.co/mistralai/Mixtral-8x7B-Instruct-v0.1)

### Setting Up Your Environment

1.  **Create a config file**

    Create a file named `gintonic-config.json` in your home directory:

    ```json
    {
      "wallet_address": "YOUR_WALLET_ADDRESS_HERE",
      "gpu_allocation": 70
    }
    ```

    Replace `YOUR_WALLET_ADDRESS_HERE` with your actual wallet address. The `gpu_allocation` value sets the percentage of your GPU you want to dedicate to gintonic (70% is a good starting point).
2.  **Start your node**

    Run the following command to start your gintonic Distillery node:

    ```bash
    docker run -d --gpus all -v ~/gintonic-config.json:/app/config.json gintonic/distillery:latest
    ```

And that's it! Your GPU is now part of the gintonic network, ready to crunch some AI tasks and earn you some $GIN.

{% hint style="info" %}
**First time jitters?** It's normal to feel a bit nervous when setting this up for the first time. If you run into any issues, check out our Troubleshooting section or reach out on our community Discord.
{% endhint %}

In the next section, we'll cover how to monitor your node and track your earnings. Happy distilling!
