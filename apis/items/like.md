# Like

{% api-method method="post" host="https://zirmi.com" path="/api/items/<item\_pk>/like/" %}
{% api-method-summary %}
Like
{% endapi-method-summary %}

{% api-method-description %}
아이템 좋아요를 위한 API 
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
좋아요.
{% endapi-method-response-example-description %}

```javascript
{
    "user": {
        "pk": 11,
        "email": "ksw128@naver.com",
        "generation": "20대",
        "gender": "여성"
    },
    "item": {
        "id": 1,
        "user": {
            "email": "rainsound128@gmail.com"
        },
        "public_visibility": true,
        "like_users": [],
        "category": "디지털/가전제품",
        "is_purchase": false,
        "purchase_date": null,
        "created_time": "2018-06-18T14:19:39.945421",
        "modified_time": "2018-06-18T14:19:39.947433",
        "name": "애플 맥북프로 레티나 MJLQ2KH/A 리프레시15년형 c",
        "purchase_url": "http://item.gmarket.co.kr/DetailView/Item.asp?goodscode=784175855",
        "price": 1974830,
        "img": "/media/items/600_oRzbBpu.jpeg"
    },
    "result": false
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
없는 item_pk 값일 경우.
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



