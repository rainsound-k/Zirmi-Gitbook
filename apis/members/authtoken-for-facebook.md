# AuthToken for facebook

{% api-method method="post" host="https://zirmi.com" path="/api/members/facebook-auth-token/" %}
{% api-method-summary %}
AuthToken for facebook
{% endapi-method-summary %}

{% api-method-description %}
페이스북 로그인을 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="access\_token" type="string" required=true %}
페이스북 액세스 토큰
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
 페이스북 로그인 성공. 
{% endapi-method-response-example-description %}

```javascript
{
    "token": "bd47de4bd01bc9608ed7554c1f1fb7ac438583bd",
    "user": {
        "pk": 29,
        "email": "rainsound128@gmail.com",
        "generation": "20대",
        "gender": "남성"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
case1: access\_token 이 없을 경우.   
case2: access\_token의 값이 빈칸일 경우.   
case3: access\_token이 틀을 경우. 
{% endapi-method-response-example-description %}

```javascript
{
    "_comment": "case1",
    "access_token": [
        "이 필드는 필수 항목입니다."
    ] 
}


{
    "_comment": "case2",
    "access_token": [
        "이 필드는 blank일 수 없습니다."
    ]
}


{
    "_comment": "case3",
    "detail": [
        "액세스 토큰이 올바르지 않습니다"
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

