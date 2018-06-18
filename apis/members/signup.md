# SignUp

{% api-method method="post" host="https://zirmi.com" path="/api/members/signup/" %}
{% api-method-summary %}
Sign Up
{% endapi-method-summary %}

{% api-method-description %}
 회원 가입을 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
이메일 형식  
ex\) aaa@aaa.com
{% endapi-method-parameter %}

{% api-method-parameter name="password1" type="string" required=true %}
6자리 이상
{% endapi-method-parameter %}

{% api-method-parameter name="password2" type="string" required=true %}
6자리 이상
{% endapi-method-parameter %}

{% api-method-parameter name="generation" type="integer" required=false %}
10대 이하 : 1  
20대 : 2  
30대 : 3  
40대 : 4  
50대 이상 : 5
{% endapi-method-parameter %}

{% api-method-parameter name="gender" type="string" %}
남성 : m  
여성 : f
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
유저 생성 완료.
{% endapi-method-response-example-description %}

```javascript
{
    "email": "rainsound128@gmail.com",
    "generation": "2",
    "gender": "m"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
email or password1 or password2 가 없는 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "email": [
        "이 필드는 필수 항목입니다."
    ],
    "password1": [
        "이 필드는 필수 항목입니다."
    ],
    "password2": [
        "이 필드는 필수 항목입니다."
    ],
}
```
{% api-method-response-example-description %}
email or password1 or password2 의 값이 빈칸일 경우.  
{% endapi-method-response-example-description %}

```javascript
{
    "email": [ 
        "이 필드는 blank일 수 없습니다." 
    ], 
    "password1": [ 
        "이 필드는 blank일 수 없습니다." 
    ], 
    "password2": [ 
        "이 필드는 blank일 수 없습니다." 
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

