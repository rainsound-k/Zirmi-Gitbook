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
case1: email or password1 or password2 가 없는 경우.  
case2: email or password1 or password2 의 값이 빈칸일 경우.   
case3: email 형식이 아닐 경우.   
case4: 이미 email 이 존재할 경우.   
case5: password1 과 password2 의 값이 다를 경우.   
case6: password1 or password2 의 글자수가 6자 미만일 경우. 
{% endapi-method-response-example-description %}

```javascript
{
    "_comment": "case1",
    "email": [
        "이 필드는 필수 항목입니다."
    ],
    "password1": [
        "이 필드는 필수 항목입니다."
    ],
    "password2": [
        "이 필드는 필수 항목입니다."
    ]
}


{
    "_comment": "case2",
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


{
    "_comment": "case3",
    "email": [
        "유효한 이메일 주소를 입력하십시오."
    ]
}


{
    "_comment": "case4",
    "email": [
        "detail": "이미 존재하는 email 입니다"
    ]
}


{
    "_comment": "case5",
    "detail": [
        "비밀번호와 비밀번호 확인란이 같지 않습니다"
    ]
}


{
    "_comment": "case6",
    "password1": [
        "이 필드의 글자 수가 적어도 6 이상인지 확인하십시오."
    ],
    "password2": [
         "이 필드의 글자 수가 적어도 6 이상인지 확인하십시오."
     ]
 }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



