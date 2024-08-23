---
description: >-
  Detailed descriptions of each endpoint, their functionality, required
  parameters, and example requests and responses.
---

# Using the API

## API Endpoints (WebSocket)

### Start a New Chat

**Endpoint URL:** /interaction-model/message

**Description:** Initiate a new chat session with the AI assistant. This endpoint creates a unique chat session ID.&#x20;

**Parameters:** In order to start a chat with a model you need to know the 'chatId'

**Request Parameter**

* API-key

**Request Body**

```
{
   "event": "startChat",
  "data": {
    "chatId"?: <chat_id>, // optional
    "apiKey": <api_key>
   }
} 
```

To receive a new chat parameter ('chatId'), you must send a request that does not contain a field indicating this parameter.

The chat lifetime of each chat is determined from the last message sent and is 24 hours by default. If a chat does not receive new messages within 24 hours, it will be automatically deleted and an error message will be returned when you try to access it: "Chat not found".

### Send a Message (WebSocket)

**Endpoint URL:** /interaction-model/message

**Description:** Send a message to the AI assistant within an existing chat session. The AI assistant will process the message and respond accordingly.

**Parameters:**

* 'chat-id'

**Request Body**

```
{
  "event": "generate",
  "data": {
    "inputs": <message_to_model>,
    "chatId": <chat-id>, // required
    "api-key": <api-key> 
  }
}
```

### Get Chat Response (WebSocket)

**Endpoint URL:** /interaction-model/message

**Description:** Get the AI assistant's response to a specific message within a chat session.

**Parameters:** -

**Request Body**

If the request is successful, the server will send several messages (the number of messages will depend on the length of the model response) of the appropriate type.

```
{
  "content": <chunk_response_model>,
}
```

If an error occurs while processing the request, the server response will contain the following:

```
{
  "content": <chunk_response_model>,
  "stop": true
}
```

where&#x20;

* stop – indicator of whether this message is the last message in the model response;
* balance – new balance of the current user after the request has been fulfilled.

If an error occurs when the maximum number of tokens in the model response is reached, the response will have the following:

```
{
  "event": "maxLimitTokens",
  "message": "The maximum token limit in the model response has been exceeded. To continue using the chat, you must start a new session. When starting a new session, the current session will be lost."
}
```

In case the petals chat server-side script stops working due to incorrect data passed in the request, an error message will be sent.
