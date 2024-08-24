# Troubleshooting

## Troubleshooting

Even the smoothest systems hit a bump now and then. When that happens, we've got your back. This guide will help you diagnose and solve common issues you might encounter while using the Inference Subchain.

### Common Issues and Solutions

#### 1. Connection Problems

**Symptom**: Unable to establish a WebSocket connection.

**Possible Causes and Solutions**:

a) **Invalid API Key**

* Double-check your API key.
* Ensure you're using the correct key for the environment (development/production).

b) **Network Issues**

* Check your internet connection.
* If you're behind a firewall, ensure it's not blocking WebSocket connections.

c) **Server Downtime**

* Check our [status page](https://status.gintonic.ai) for any ongoing issues.

**Code to Test Connection**:

```python
from gintonic import InferenceClient

try:
    client = InferenceClient(api_key="your_api_key_here")
    client.test_connection()
    print("Connection successful!")
except Exception as e:
    print(f"Connection failed: {str(e)}")
```

#### 2. Rate Limiting

**Symptom**: Receiving 429 (Too Many Requests) errors.

**Solution**:

* Implement exponential backoff in your requests.
* If you consistently hit rate limits, consider upgrading your plan.

**Example Backoff Implementation**:

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
            time.sleep(2 ** attempt)  # Exponential backoff
```

#### 3. Unexpected End of Chat Session

**Symptom**: Chat session ends unexpectedly or returns an error about maximum tokens.

**Possible Causes and Solutions**:

a) **Exceeded Maximum Tokens**

* The conversation has reached the model's token limit.
* Start a new chat session for continued interaction.

b) **Inactivity Timeout**

* Chat sessions automatically end after 24 hours of inactivity.
* Implement a keep-alive mechanism or start a new session if needed.

#### 4. Unexpected Model Outputs

**Symptom**: The model's responses are irrelevant or seem to ignore context.

**Possible Causes and Solutions**:

a) **Unclear or Ambiguous Prompts**

* Refine your prompts to be more specific and provide necessary context.

b) **Inconsistent Chat History**

* Ensure you're sending the correct chat ID with each request.
* Consider summarizing long conversations to maintain context without exceeding token limits.

#### 5. High Latency

**Symptom**: Responses are taking longer than expected.

**Possible Causes and Solutions**:

a) **Complex Queries**

* Break down complex tasks into smaller, more manageable requests.

b) **Network Issues**

* Check your network connection and latency to our servers.

c) **High System Load**

* If persistent, it might indicate high load on our systems. Check our [status page](https://status.gintonic.ai).

### Error Message Explanations

Here's a quick reference for common error messages you might encounter:

| Error Code | Message                 | Explanation                                  | Solution                                                                    |
| ---------- | ----------------------- | -------------------------------------------- | --------------------------------------------------------------------------- |
| 401        | "Unauthorized"          | Invalid or missing API key                   | Check your API key and ensure it's correctly included in the request header |
| 403        | "Forbidden"             | Insufficient permissions or depleted balance | Check your account balance and permissions                                  |
| 404        | "Chat Not Found"        | The specified chat ID doesn't exist          | Verify the chat ID or start a new chat session                              |
| 429        | "Too Many Requests"     | You've exceeded the rate limit               | Implement backoff and retry logic                                           |
| 500        | "Internal Server Error" | An unexpected error occurred on our end      | If persistent, contact our support team                                     |

### Debugging Tools

To help diagnose issues, we provide several debugging tools:

1.  **Verbose Mode**: Enable detailed logging in the client.

    ```python
    client = InferenceClient(api_key="your_key", verbose=True)
    ```
2.  **Request ID**: Each request has a unique ID. Include this when contacting support.

    ```python
    response = client.send_message(chat_id, "Hello")
    print(f"Request ID: {response.request_id}")
    ```
3.  **Health Check Endpoint**: Use this to verify the service status.

    ```python
    health_status = client.check_health()
    print(f"Service Status: {health_status}")
    ```

### Still Stuck?

If you've tried these solutions and are still experiencing issues:

1. Check our FAQ page for more common questions and answers.
2. Visit our Community Forum to see if others have encountered and solved similar issues.
3. If all else fails, don't hesitate to contact our support team. We're here to help!

Remember to include as much relevant information as possible:

* Your API key (don't share the full key, just the last 4 characters)
* The request ID (if applicable)
* A description of the issue
* Any error messages you're receiving
* Steps to reproduce the problem

We're committed to providing a smooth experience with the Inference Subchain. Your feedback helps us improve, so don't be shy about reporting issues or suggesting improvements!
