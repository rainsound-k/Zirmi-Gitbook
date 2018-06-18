# Login

{% api-method method="post" host="https://zirmi.com" path="/api/members/login/" %}
{% api-method-summary %}
Login
{% endapi-method-summary %}

{% api-method-description %}
 로그인을 위한 API 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
 이메일 
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
비밀번호 
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
로그인 성공. 
{% endapi-method-response-example-description %}

```javascript
{
    "token": "4b56b6fc26555a96bef2ee9012f93129e3925b99",
    "user": {
        "pk": 11,
        "email": "rainsound128@gmail.com",
        "generation": "20대",
        "gender": "남성"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
case1: .
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



