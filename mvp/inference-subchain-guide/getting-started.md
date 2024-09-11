---
description: >-
  Step-by-step guide to set up and use the Gintonic inference subchain. Learn
  how to create an account, obtain API keys, and make your first API call.
---

# Getting Started

## Getting Started with the inference subchain

Ready to harness the power of distributed AI inference? Let's get you set up and running in no time.

#### Inspiration: AI Speakeasy

Now that you've set up your environment, you might be wondering what you can build. For inspiration, check out [AI Speakeasy](https://aispeakeasy.com), a demo application built using the Gintonic inference subchain.

AI Speakeasy features an AI bartender powered by the Mistral model, demonstrating how you can create interactive, chat-based AI applications. It's a great example of what's possible with the technology you've just set up.

As you continue your journey with Gintonic, keep AI Speakeasy in mind as a benchmark for the kind of engaging, responsive AI applications you can create.

[Explore AI Speakeasy](https://aispeakeasy.com)

### Prerequisites

Before you start firing off API requests, make sure you've got these basics covered:

1. **Gintonic Inference Account**: If you haven't already, sign up at [https://console.gintonic.ai/inference](https://console.gintonic.ai/inference). It's quick, painless, and free to create an account.
2. **API Key**: You'll need this to authenticate your requests. Here's how to get one:
   * Log into your Gintonic account.
   * Navigate to the 'API Keys' section.
   * Click 'Generate New Key'.
   * Copy and save your key somewhere safe. We'll only show it to you once!
3. **Wallet Setup**: You'll need a blockchain wallet to handle transactions on the platform.
   * We recommend using MetaMask. If you don't have it, grab it from [metamask.io](https://metamask.io/)
   * Once installed, connect your wallet to the Gintonic platform.
4. **$GIN**: Make sure you have some $GIN in your wallet. These are used to pay for inference requests.

### System Requirements

Before you begin, ensure your system meets the following minimum requirements:

* **Operating System**: Linux Ubuntu 20.04 or later.
* **GPU**: Minimum 2G VRAM.
* **Drivers**: Video card drivers and the 'nvidia-smi' package must be installed.
* **HuggingFace**: An account on HuggingFace and an Access Token.
* **Blockchain**: A valid blockchain wallet address.

### Installation Process

To set up the inference subchain on your system:

1. Download the installer from [this link](https://thinkchain-backend.sfxdx.com/distillery-download)&#x20;
2. Run the installer. It will automatically:
   * Install additional dependencies not specified in the prerequisites.
   * Create a worker that connects to the required swarm.
   * Calculate the number of model blocks occupied by the worker.
   * Send the worker's address and ID to the blockchain for future awarding.

### Quick Start Guide

Let's make your first API call to the inference subchain:

1.  **Install the gintonic SDK**

    We've got SDKs for popular languages. Let's use Python for this example:

    ```bash
    pip install gintonic-sdk
    ```
2.  **Initialize the client**

    ```python
    from gintonic import InferenceClient

    client = InferenceClient(api_key="your_api_key_here")
    ```
3.  **Start a chat session**

    ```python
    chat_id = client.start_chat()
    ```
4.  **Send a message**

    ```python
    response = client.send_message(chat_id, "Tell me a joke about AI")
    print(response.content)
    ```
5.  **End the chat session**

    ```python
    client.end_chat(chat_id)
    ```

Congratulations! You've just made your first inference request using the Gintonic inference subchain.

### What's Next?

* Dive into our API Reference to explore all available endpoints.
* Check out Best Practices to optimize your usage.
* Got questions? Head over to our FAQs or Troubleshooting sections.

Remember, we're all about making AI inference accessible and affordable. If you run into any roadblocks, don't hesitate to reach out to our support team.

Happy inferencing!
