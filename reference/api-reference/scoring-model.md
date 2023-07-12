# Scoring Model

## Returning scoring

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
