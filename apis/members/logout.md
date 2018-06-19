# Logout

{% api-method method="post" host="https://zirmi.com" path="/api/members/logout/" %}
{% api-method-summary %}
Logout
{% endapi-method-summary %}

{% api-method-description %}
 로그아웃을 위한 API
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
로그아웃 성공.
{% endapi-method-response-example-description %}

```javascript
{
    "detail": "정상적으로 로그아웃 되었습니다"
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



