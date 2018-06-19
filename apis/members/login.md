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
{% api-method-form-data-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
이메일
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
비밀번호
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
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

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
case1: email or password가 없는 경우.  
case2: email or password의 값이 빈칸일 경우.  
case3: email 형식이 아닐 경우.  
case4: email은 맞고 password가 틀렸을 경우.  
case5: email이 틀렸을 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "_comment": "case1",
    "email": [
        "이 필드는 필수 항목입니다."
    ],
    "password": [
        "이 필드는 필수 항목입니다."
    ]
}


{
    "_comment": "case2",
    "email": [
        "이 필드는 blank일 수 없습니다."
    ],
    "password": [
        "이 필드는 blank일 수 없습니다."
    ]
}


{
    "_comment": "case3",
    "email": [
        "유효한 이메일 주소를 입력하십시오."
    ]
}


{
    "_comment": "case4",
    "detail": [
        "올바르지 않은 password 입니다"
    ]
}


{
    "_comment": "case5",
    "detail": [
        "가입된 email이 없습니다"
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

