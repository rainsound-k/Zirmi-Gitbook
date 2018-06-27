# List

{% api-method method="get" host="https://zirmi.net" path="/frontend-api/items/complete/list/" %}
{% api-method-summary %}
List
{% endapi-method-summary %}

{% api-method-description %}
구매 완료한 아이템 리스트를 위한 API  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token &lt;발급 받은 토큰 key&gt;
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="page" type="integer" %}
page 숫자\(page 당 아이템 5개\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
구매 완료한 아이템 리스 정상 출력.
{% endapi-method-response-example-description %}

```javascript
{
    "count": 3,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 19,
            "user": {
                "email": "rainsound128@gmail.com"
            },
            "public_visibility": false,
            "like_users": [],
            "category": "기타",
            "is_purchase": true,
            "purchase_date": "2018-06-19T17:03:53.157507",
            "created_time": "2018-06-19T17:03:43.925287",
            "modified_time": "2018-06-19T17:03:53.163666",
            "name": "2017 뉴아이패드 9.7 필름 강화유리 5세대",
            "purchase_url": "http://itempage3.auction.co.kr/DetailView.aspx?ItemNo=B527111076",
            "price": 11500,
            "img": "http://localhost:8000/media/items/15234081e6.jpeg"
        },
        {
            "id": 17,
            "user": {
                "email": "rainsound128@gmail.com"
            },
            "public_visibility": false,
            "like_users": [],
            "category": "디지털/가전제품",
            "is_purchase": true,
            "purchase_date": "2018-06-19T17:03:55.259451",
            "created_time": "2018-06-19T17:03:40.211655",
            "modified_time": "2018-06-19T17:03:55.261806",
            "name": "애플 맥북프로 레티나 MJLQ2KH/A 리프레시15년형 c",
            "purchase_url": "http://item.gmarket.co.kr/DetailView/Item.asp?goodscode=784175855",
            "price": 1974830,
            "img": "http://localhost:8000/media/items/600_oRzbBpu.jpeg"
        },
        {
            "id": 16,
            "user": {
                "email": "rainsound128@gmail.com"
            },
            "public_visibility": false,
            "like_users": [],
            "category": "디지털/가전제품",
            "is_purchase": true,
            "purchase_date": "2018-06-19T17:03:57.163842",
            "created_time": "2018-06-19T17:03:36.923068",
            "modified_time": "2018-06-19T17:03:57.170804",
            "name": "애플 맥북프로 레티나 MJLQ2KH/A 리프레시15년형 c",
            "purchase_url": "http://itempage3.auction.co.kr/DetailView.aspx?ItemNo=B524497031",
            "price": 2020900,
            "img": "http://localhost:8000/media/items/150f2809c6.jpeg"
        }
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

