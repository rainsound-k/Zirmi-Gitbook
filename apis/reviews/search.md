# Search

{% api-method method="get" host="https://zirmi.com" path="/api/reviews/search/" %}
{% api-method-summary %}
Search
{% endapi-method-summary %}

{% api-method-description %}
리뷰 검색을 위한 API 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="sort" type="string" required=true %}
제목으로 검색: title  
내용으로 검색: content  
아이템명으로 검색: item  
전체 검색: all  
{% endapi-method-parameter %}

{% api-method-parameter name="keyword" type="string" required=true %}
검색할 내용  
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
리뷰 검색 성.
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

