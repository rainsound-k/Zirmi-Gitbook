# List, Create

{% api-method method="get" host="https://zirmi.com" path="/api/items/" %}
{% api-method-summary %}
List
{% endapi-method-summary %}

{% api-method-description %}
아이템 리스트를 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="page" type="integer" required=false %}
 page 숫자\(page 당 아이템 5개\)
{% endapi-method-parameter %}

{% api-method-parameter name="ordering" type="string" required=false %}
좋아요 많은순: -like\_users   
좋아요 적은순: like\_users
{% endapi-method-parameter %}

{% api-method-parameter name="user\_\_generation" type="integer" %}
10대 이하 : 1   
20대 : 2   
30대 : 3   
40대 : 4   
50대 이상 : 5
{% endapi-method-parameter %}

{% api-method-parameter name="user\_\_gender" type="string" %}
남성 : m   
여성 : f
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
리스트 출.
{% endapi-method-response-example-description %}

```javascript
{
    "name": "Cake's name",
    "recipe": "Cake's recipe name",
    "cake": "Binary cake"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://zirmi.com" path="/api/items/" %}
{% api-method-summary %}
Create
{% endapi-method-summary %}

{% api-method-description %}
 아이템 생성을 위한 API 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



