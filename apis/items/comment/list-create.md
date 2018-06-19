# List, Create

{% api-method method="get" host="https://zirmi.com" path="/api/items/<item\_pk>/comment/" %}
{% api-method-summary %}
List
{% endapi-method-summary %}

{% api-method-description %}
아이템별로 댓글 리스트 확인을 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="item\_pk" type="integer" required=true %}
item pk 값
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="page" type="string" required=false %}
page 숫자\(page 당 댓글 5개\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
댓글 리스트 정상 출력.
{% endapi-method-response-example-description %}

```javascript
{
    "count": 3,
    "next": null,
    "previous": null,
    "results": [
        {
            "pk": 1,
            "user": {
                "email": "rainsound128@gmail.com"
            },
            "content": "좋은듯?"
        },
        {
            "pk": 2,
            "user": {
                "email": "ksw128@naver.com"
            },
            "content": "정말 좋습니다"
        },
        {
            "pk": 3,
            "user": {
                "email": "ksw128@naver.com"
            },
            "content": "진짜 좋습니다"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://zirmi.com" path="/api/items/<item\_pk>/comment/" %}
{% api-method-summary %}
Create
{% endapi-method-summary %}

{% api-method-description %}
댓글 생성을 위한 API
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

{% api-method-form-data-parameters %}
{% api-method-parameter name="content" type="string" required=true %}
댓글 내용
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
댓글 생성 성공.  
{% endapi-method-response-example-description %}

```javascript
{
    "pk": 4,
    "user": {
        "email": "rainsound128@gmail.com"
    },
    "content": "굿굿"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
content가 없는 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "content": [
        "이 필드는 필수 항목입니다."
    ]
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

