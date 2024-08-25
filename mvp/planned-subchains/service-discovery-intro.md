# service discovery intro

The gintonic **Service Discovery Subchain** is being conceptualized as a critical component for enabling seamless interaction between various services within the ecosystem. This subchain is intended to provide a robust framework for identifying and accessing different AI services and resources, making it easier for developers to find and integrate the tools they need.

The primary focus of the Service Discovery Subchain will be to create a dynamic registry where available services can be cataloged and retrieved efficiently. Whether it’s locating specific APIs, data sources, or computational resources, this subchain aims to streamline the process, ensuring that all components of the ecosystem can communicate and work together effectively.

In addition to simplifying access, the Service Discovery Subchain is expected to enhance the flexibility and scalability of AI solutions by allowing services to be discovered and utilized on demand. This could significantly reduce the time required to develop and deploy AI applications, as developers would be able to quickly locate and leverage the necessary resources, fostering a more integrated and responsive AI ecosystem.

## Create a new user

<mark style="color:green;">`POST`</mark> `/users`

\<Description of the endpoint>

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name   | Type   | Description      |
| ------ | ------ | ---------------- |
| `name` | string | Name of the user |
| `age`  | number | Age of the user  |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "id": 1,
  "name": "John",
  "age": 30
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}
