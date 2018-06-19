# Item add from public list

{% api-method method="get" host="https://zirmi.com" path="/api/items/public/add/" %}
{% api-method-summary %}
Item add from public list
{% endapi-method-summary %}

{% api-method-description %}
전체 공개 아이템을 내 아이템에 추가하기 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token &lt;발급 받은 토큰 key&gt;
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="item\_pk" type="string" required=true %}
item pk 값
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
아이템 정상적으로 추가.
{% endapi-method-response-example-description %}

```javascript
{
    "detail": "내 아이템에 추가되었습니다"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
case1: item\_pk가 없는 경우.  
case2: item\_pk의 user일 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "_comment": "case1",
    "detail": "item_pk를 입력해주세요"
}


{
    "_comment": "case2",
    "detail": "이미 존재합니다"
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

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
없는 item\_pk 값일 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "detail": "찾을 수 없습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

