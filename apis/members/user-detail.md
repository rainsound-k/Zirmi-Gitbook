# User detail

{% api-method method="get" host="https://zirmi.com" path="/api/members/info/" %}
{% api-method-summary %}
User detail
{% endapi-method-summary %}

{% api-method-description %}
 유저 정보를 위한 API 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token &lt;발급 받은 토큰 key&gt; 
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
토큰 정상 인.
{% endapi-method-response-example-description %}

```javascript
{
    "pk": 29,
    "email": "rainsound128@gmail.com",
    "generation": "20대",
    "gender": "남성"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
case1: header에 Token 값이 없을 경우.   
case2: Token 값이 틀렸을 경우. 
{% endapi-method-response-example-description %}

```javascript
{   
    "_comment": "case1",
    "detail": "자격 인증데이터(authentication credentials)가 제공되지 않았습니다."
}


{
    "_comment": "case2",
    "detail": "토큰이 유효하지 않습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



