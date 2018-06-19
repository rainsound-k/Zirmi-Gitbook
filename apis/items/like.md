# Like

{% api-method method="post" host="https://zirmi.com" path="/api/items/<item\_pk>/like/" %}
{% api-method-summary %}
Like
{% endapi-method-summary %}

{% api-method-description %}
아이템 좋아요를 위한 API 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="item\_pk" type="integer" required=true %}
item pk 값 
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token &lt;발급 받은 토큰 key&gt; 
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "name": "Cake's name",
    "recipe": "Cake's recipe name",
    "cake": "Binary cake"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "message": "Ain't no cake like that."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



