---
description: >-
  Step-by-step instructions to join the gintonic distillery network. Learn
  system requirements, installation process, and initial setup for your node.
---

# Getting Started

## Getting Started with gintonic distillery

Ready to put your GPU to work? Great! This guide will walk you through the process of joining the gintonic distillery network. Don't worry if you're not a tech wizard - we've designed this process to be as straightforward as possible.

### System Requirements

Before we dive in, let's make sure your system is up to the task:

* **GPU**: NVIDIA GPU with at least 8GB of VRAM
* **Operating System**: Ubuntu 20.04 LTS or later
* **Storage**: At least 50GB of free disk space
* **Internet**: Stable broadband connection

The Petals framework, which is designed for distributed inference and fine-tuning of large language models, primarily supports NVIDIA GPUs that are compatible with CUDA. Here is a list of NVIDIA GPUs that are generally supported, provided they have sufficient VRAM (typically 8 GB or more is recommended for larger models):

#### Supported NVIDIA GPUs:

1. **GeForce Series:**
   * RTX 4090, RTX 4080, RTX 4070 Ti
   * RTX 3090, RTX 3080, RTX 3070, RTX 3060 (and Ti variants)
   * RTX 2080 Ti, RTX 2080, RTX 2070, RTX 2060 (and Ti variants)
   * GTX 1660, GTX 1650 (with lower performance due to limited VRAM)
   * GTX 1080 Ti, GTX 1080, GTX 1070, GTX 1060 (older, but still usable for smaller tasks)
2. **Quadro Series:**
   * Quadro RTX 8000, RTX 6000, RTX 5000
   * Quadro P6000, P5000 (older models with large VRAM)
3. **Tesla Series:**
   * Tesla V100, P100 (high-performance, data-center GPUs)
4. **A-Series (Data Center GPUs):**
   * A100, A40, A30 (high-end, designed for AI workloads)
5. **Titan Series:**
   * Titan RTX, Titan V, Titan Xp (high VRAM, consumer-grade GPUs with excellent performance)

#### Key Requirements:

* **CUDA Compatibility:** The GPU must support CUDA 11.3 or newer, as Petals relies on the CUDA toolkit for parallel computing capabilities.
* **VRAM:** For larger models like those supported by Petals (e.g., BLOOM, Llama), having at least 8 GB of VRAM is recommended to handle the model’s requirements efficiently.

These GPUs are widely supported and provide the best performance for running distributed model inference and fine-tuning with the Petals framework. For optimal performance, using the latest drivers and CUDA versions is recommended【7†source】【9†source】.

{% hint style="warning" %}
While it's possible to run on other setups, we've optimized for these specifications. Your mileage may vary with different configurations.
{% endhint %}

### Creating a gintonic distillery Account

Before setting up your node, you'll need to create a gintonic distillery account:

1. Visit [https://console.gintonic.ai/distillery](https://console.gintonic.ai/distillery)
2. Click on the "Sign Up" button
3. Fill in the required information:
   * Email address
   * Password (make sure it's strong and unique)
   * Confirm password
4. Read and accept the Terms of Service and Privacy Policy
5. Click "Create Account"
6. Verify your email address by clicking the link sent to your inbox
7. Once verified, log in to your new gintonic distillery account

{% hint style="info" %}
Keep your account credentials safe and secure. You'll need them to manage your node and access your earnings.
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
4.  **Pull the gintonic distillery image**

    Grab our Docker image:

    
    ```bash    

    docker pull gintonic/distillery:latest 
    ```
5. **Set up your wallet**

    You'll need an Ethereum-compatible wallet to receive your $GIN. \
    If you don't have one, we recommend [MetaMask](https://metamask.io/). Make sure to keep your private keys safe and secure!


6. **Set up HuggingFace**

    - Create an account on [HuggingFace](https://huggingface.co/)
    - Create an Access Token in your HuggingFace account settings
    - Confirm access to this repository: [Mixtral-8x7B-Instruct-v0.1](https://huggingface.co/mistralai/Mixtral-8x7B-Instruct-v0.1)

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

    Run the following command to start your gintonic distillery node:

    ```bash
    docker run -d --gpus all -v ~/gintonic-config.json:/app/config.json gintonic/distillery:latest
    ```

And that's it! Your GPU is now part of the gintonic network, ready to crunch some AI tasks and earn you some $GIN.

{% hint style="info" %}
**First time jitters?** It's normal to feel a bit nervous when setting this up for the first time. If you run into any issues, check out our Troubleshooting section or reach out on our community [Discord Channel](https://discord.gg/sGkz4RHz).
{% endhint %}

In the next section, we'll cover how to monitor your node and track your earnings. Happy distilling!
