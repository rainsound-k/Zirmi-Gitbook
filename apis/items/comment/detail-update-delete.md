# Detail, Update, Delete

{% api-method method="get" host="https://zirmi.com" path="/api/items/comment/<comment\_pk>/" %}
{% api-method-summary %}
Detail
{% endapi-method-summary %}

{% api-method-description %}
댓글 상세 정보를 위한 API 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="comment\_pk" type="integer" required=true %}
comment pk 값   
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
댓글 상세 정보 정상 출력. 
{% endapi-method-response-example-description %}

```javascript
{
    "pk": 1,
    "user": {
        "rainsound128@gmail.com"
    },
    "content": "좋은듯?"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
없는 comment\_pk 값일 경우.
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

{% api-method method="put" host="https://zirmi.com" path="/api/items/comment/<comment\_pk>/" %}
{% api-method-summary %}
Update
{% endapi-method-summary %}

{% api-method-description %}
 댓글 업데이트를 위한 API  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="comment\_pk" type="integer" required=true %}
comment pk 값   
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token &lt;발급 받은 토큰 key&gt;  
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="content" type="string" required=false %}
댓글 내용
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
댓글 업데이트 성공.
{% endapi-method-response-example-description %}

```javascript
{
    "pk": 1,
    "user": {
        "email": "rainsound128@gmail.com"
    },
    "content": "좋네"
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

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
댓글 user가 아닐 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "detail": "이 작업을 수행할 권한(permission)이 없습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
없는 comment\_pk 값일 경우.
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

{% api-method method="delete" host="https://zirmi.com" path="/api/items/comment/<comment\_pk>/" %}
{% api-method-summary %}
Delete
{% endapi-method-summary %}

{% api-method-description %}
댓글 삭제를 위한 API  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="comment\_pk" type="integer" required=true %}
comment pk 값  
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token &lt;발급 받은 토큰 key&gt;  
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}
댓글 삭제 성공.
{% endapi-method-response-example-description %}

```javascript

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

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
댓글의 user가 아닐 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "detail": "이 작업을 수행할 권한(permission)이 없습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
없는 comment\_pk 값일 경우.
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



