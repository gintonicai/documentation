# API Reference

## API Reference

Welcome to the nuts and bolts of the Inference Subchain API. This is where you'll find all the details you need to integrate our service into your applications. Let's dive in!

### Base URL

All API requests should be made to the following base URL:

wss://api.gintonic.ai/inference/v1



### Authentication

Before you start making requests, you'll need to authenticate. We use API keys for this.

*   Include your API key in the header of each request:

    ```
    Authorization: Bearer YOUR_API_KEY
    ```
* Don't have an API key yet? Head over to the Getting Started guide to learn how to get one.

#### API Key Management

* You can have up to 5 API keys active on your account at any given time
* When generating a new API key, it will only be shown once. Make sure to copy and store it securely
* There is no confirmation prompt when deleting a key, so be careful when managing your keys
* If you try to delete a key that is currently in use, you'll see a warning: "API key is in use"

### WebSocket Endpoints

Our API uses WebSockets for real-time communication. Here's what you need to know:

#### Base URL

```
wss://api.gintonic.ai/inference/v1
```

#### 1. Start a New Chat

Initiates a new chat session with the AI assistant.

* **Endpoint:** `/interaction-model/message`
* **Event:** `startChat`

**Request:**

```json
{
  "event": "startChat",
  "data": {
    "chatId": "<chat_id>",  // Optional. If not provided, a new chat will be created.
    "apiKey": "<api_key>"
  }
}
```

**Response:**

```json
{
  "chatId": "<new_chat_id>",
  "message": "Chat session started successfully"
}
```

#### 2. Send a Message

Sends a message to the AI assistant within an existing chat session.

* **Endpoint:** `/interaction-model/message`
* **Event:** `generate`

**Request:**

```json
{
  "event": "generate",
  "data": {
    "inputs": "<message_to_model>",
    "chatId": "<chat_id>",
    "apiKey": "<api_key>"
  }
}
```

#### 3. Get Chat Response

Retrieves the AI assistant's response to your message.

* **Endpoint:** `/interaction-model/message`

**Response:**

The server will send multiple messages, each containing a chunk of the response:

```json
{
  "content": "<chunk_response_model>"
}
```

The final message will include a `stop` flag:

```json
{
  "content": "<final_chunk_response_model>",
  "stop": true,
  "balance": "<new_balance>"
}
```

#### Chat Session Management

* The chat lifetime is determined from the last message sent and is 24 hours by default
* If a chat does not receive new messages within 24 hours, it will be automatically deleted
* Attempting to access a deleted chat will return an error message: "Chat not found"

#### WebSocket Communication

* Responses may come in multiple messages, especially for longer outputs
* The final message in a response will include a `stop: true` flag

### Error Handling

When things go sideways (hey, it happens), here's what you might see:

#### General Error Format

```json
{
  "error": {
    "code": "<error_code>",
    "message": "<error_description>"
  }
}
```

#### Common Error Codes

* `401`: Authentication error. Check your API key.
* `403`: Insufficient balance. Time to top up!
* `404`: Chat not found. Double-check your chat ID.
* `429`: Too many requests. Slow down, speed racer!
* `500`: Server error. Give us a moment to sort things out.

#### Special Cases

If you hit the maximum token limit, you'll get this message:

```json
{
  "event": "maxLimitTokens",
  "message": "The maximum token limit in the model response has been exceeded. To continue using the chat, you must start a new session. When starting a new session, the current session will be lost."
}
```

### Best Practices

1. **Keep Your API Key Secret**: Never share it or commit it to public repositories.
2. **Handle Reconnections**: WebSockets can disconnect. Implement reconnection logic in your client.
3. **Monitor Your Balance**: Keep an eye on your token usage to avoid interruptions.
4. **Optimize Your Prompts**: Clearer prompts generally lead to better (and often shorter) responses, saving you tokens.

### Rate Limits

* 100 requests per minute per API key
* 1000 requests per hour per API key

Exceeding these limits will result in a `429` error. If you need higher limits, drop us a line.

### Changelog

| Version | Date       | Changes                                  |
| ------- | ---------- | ---------------------------------------- |
| v1.0    | 2024-08-01 | Initial release                          |
| v1.1    | 2024-08-15 | Added support for longer context windows |

That's the rundown of our API! If you're looking to optimize your usage or dive into more advanced topics, check out our Best Practices guide.

Remember, we're here to make AI inference a breeze. If you run into any snags or have questions, don't hesitate to reach out. Happy coding!
