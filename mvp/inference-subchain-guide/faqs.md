---
description: >-
  Get answers to frequently asked questions about the gintonic Inference
  Subchain. Find quick solutions to common queries and concerns.
---

# FAQs

## Frequently Asked Questions (FAQ)

Got questions? We've got answers! Here's a roundup of the most common queries we get about the inference subchain. If you don't find what you're looking for, remember you can always reach out to our support team.

### General Questions

#### Q: What is the inference subchain?

**A:** The inference subchain is a key component of the gintonic ecosystem that provides developers with access to distributed AI inference capabilities. It acts as a bridge between your applications and our network of GPU-powered nodes, offering cost-effective and scalable AI model execution.

#### Q: How does the inference subchain differ from other AI APIs?

**A:** The main differences are:

1. Cost-efficiency: Our distributed approach typically results in lower costs.
2. Scalability: We can easily handle varying loads by leveraging our network of nodes.
3. Decentralization: Unlike centralized services, we're not dependent on a single point of failure.

#### Q: Which AI models are available on the inference subchain?

**A:** We currently support the Mistral LLM. We're constantly working on adding more models, so stay tuned to our blog for updates!

### Technical Questions

#### Q: How do I get started with the inference subchain?

**A:** Check out our Getting Started guide for a step-by-step walkthrough. In short:

1. Sign up for an account
2. Get your API key
3. Install our SDK
4. Start making API calls!

#### Q: What programming languages do you support?

**A:** Our main SDK is available for Python. We also have community-supported libraries for JavaScript, Java, and Go. Check our GitHub for the latest list.

#### Q: How do I handle rate limiting?

**A:** We recommend implementing exponential backoff in your requests. Here's a quick example:

```python
import time
from gintonic import InferenceClient, RateLimitError

def send_with_backoff(client, chat_id, message, max_retries=5):
    for attempt in range(max_retries):
        try:
            return client.send_message(chat_id, message)
        except RateLimitError:
            if attempt == max_retries - 1:
                raise
            time.sleep(2 ** attempt)
```

#### Q: What's the maximum context length for conversations?

**A:** The Mistral LLM supports up to 8,192 tokens for context. However, keep in mind that longer contexts consume more tokens and thus cost more.

### Billing and Usage

#### Q: How does billing work?

**A:** We use a pay-as-you-go model based on $GIN. 1 $GIN token is roughly equivalent to 1000 AI tokens. Check our Billing and Usage page for more details.

#### Q: What happens if I run out of tokens?

**A:** Your service will be paused until you top up your balance. We'll send you notifications as your balance gets low so you can avoid interruptions.

#### Q: Do unused tokens expire?

**A:** Nope! Your $GIN doesn't have an expiration date. They'll be there waiting for you when you need them.

#### Q: Can I set a spending limit?

**A:** Yes, you can set a monthly spending cap in your account settings. This helps prevent unexpected bills if your usage spikes.

### Performance and Optimization

#### Q: How can I optimize my prompts for better results?

**A:** Great question! Here are a few tips:

1. Be specific in your requests
2. Provide relevant context
3. Use examples when possible
4. Experiment with different phrasings

Check our Best Practices guide for more in-depth advice.

#### Q: What's the average response time for queries?

**A:** Response times can vary based on the complexity of the query and current network load. On average, you can expect responses within 1-3 seconds. If you're consistently seeing higher latency, please contact our support team.

#### Q: Can I use the inference subchain for real-time applications?

**A:** Absolutely! While it's not designed for millisecond-level responsiveness, many developers successfully use it for chatbots, content generation, and other near-real-time applications.

### Security and Compliance

#### Q: How do you handle data privacy?

**A:** We take data privacy seriously. We don't store the content of your requests or the model's responses. All data is processed in memory and then discarded. Check our Privacy Policy for more details.

#### Q: Is the inference subchain GDPR compliant?

**A:** Yes, we are GDPR compliant. We act as a data processor, and you (the developer) are the data controller. Make sure your use of our service complies with GDPR requirements for your specific application.

#### Q: How often should I rotate my API keys?

**A:** We recommend rotating your API keys at least every 90 days. You can easily generate new keys and revoke old ones from your account dashboard.

#### Q: What are the system requirements for using the inference subchain?

**A:** You'll need Linux Ubuntu 20.04 or later, a GPU with at least 2G VRAM, installed video card drivers and the 'nvidia-smi' package, a HuggingFace account with an Access Token, and a valid blockchain wallet address. Check our Getting Started guide for more details.

#### Q: How long do chat sessions last?

**A:** Chat sessions last for 24 hours from the last message sent. If no new messages are sent within 24 hours, the chat is automatically deleted.

#### Q: How many API keys can I have?

**A:** You can have up to 5 active API keys on your account at any given time. Remember to manage them carefully, as there's no confirmation prompt when deleting a key.

### Troubleshooting

#### Q: What should I do if I'm getting unexpected results from the model?

**A:** First, double-check your prompt. If the issue persists:

1. Try rephrasing your request
2. Ensure you're sending the correct chat ID for context
3. Check our Troubleshooting guide for more tips

If you're still stuck, our support team is here to help!

#### Q: The service seems slow. What can I do?

**A:** A few things to check:

1. Your internet connection
2. The complexity of your queries (simpler is often faster)

If the problem persists, please contact support with details about your use case.

Remember, if you can't find your question here, don't hesitate to ask in our Community Forum or reach out to our support team. We're always happy to help!
