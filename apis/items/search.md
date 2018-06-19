# Search

{% api-method method="get" host="https://zirmi.com" path="/api/items/search/" %}
{% api-method-summary %}
Search
{% endapi-method-summary %}

{% api-method-description %}
아이템 검색을 위한 API.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="url" type="string" required=true %}
상품 구매 링크\(URL 형식\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
상품 검색 성공.
{% endapi-method-response-example-description %}

```javascript
{
    "img_url": "http://gdimg.gmarket.co.kr/784175855/still/600?ver=0",
    "price": 2019450,
    "name": "애플 맥북프로 레티나 MJLQ2KH/A 리프레시15년형 c",
    "purchase_url": "http://item.gmarket.co.kr/DetailView/Item.asp?goodscode=784175855"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
case1: url이 없는 경우.  
case2: url의 값이 빈칸인 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "_comment": "case1",
    "detail": "검색할 url을 입력해주세요"
}


{
    "_comment": "case2",
    "detail": "url의 내용을 입력해주세요"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

