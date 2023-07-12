---
description: >-
  API scoring model is used to rank entities based on criteria. In our case it
  gets information about the user and posts scoring descision.
---

# API

{% hint style="info" %}
**Good to know:** API is now in the production stage, and have only POST function.
{% endhint %}

## Get your API keys

HTTP - [http://127.0.0.1:8000/scoring](http://127.0.0.1:8000/scoring)

## Make your first request

To make your first request, send an authenticated request to the scoring endpoint. This will return a `scoring decision.`

{% swagger baseUrl="http://127.0.0.1:8000" method="post" path="/scoring" summary="Returns Scoring Decision." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="PIN_CODE" required="true" type="String" %}
String of MAX 7 characters
{% endswagger-parameter %}

{% swagger-parameter in="body" name="TX_FID" required="true" type="Integer" %}
Integer of MAX 11 numbers 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="APP_ID" required="true" type="String" %}
String that is in brackets 

`{}`

and MAX 25 characters
{% endswagger-parameter %}

{% swagger-response status="200" description="Pet successfully created" %}
```javascript
{
    "name"="Wilson",
    "owner": {
        "id": "sha7891bikojbkreuy",
        "name": "Samuel Passet",
    "species": "Dog",}
    "breed": "Golden Retriever",
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Permission denied" %}

{% endswagger-response %}
{% endswagger %}

<img src=".gitbook/assets/file.excalidraw.svg" alt="Figure on how Scoring model works" class="gitbook-drawing">

Take a look at how you might call this method and what output to expect:

{% tabs %}
{% tab title="INPUT" %}
```javascript
[
  {
    "PIN_CODE": "qwertyu",
    "TX_FID": 12345678901,
    "APP_ID": "{q1w2e3r4t5y6u7i8o9p0asdfg}"
  }
]
```
{% endtab %}

{% tab title="OUTPU" %}
```javascript
{
    "status": 200,
    "score": 42
}
```
{% endtab %}
{% endtabs %}
