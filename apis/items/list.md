# List, Create

{% api-method method="get" host="https://zirmi.com" path="/api/items/" %}
{% api-method-summary %}
List
{% endapi-method-summary %}

{% api-method-description %}
아이템 리스트를 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="page" type="integer" required=false %}
 page 숫자\(page 당 아이템 5개\)
{% endapi-method-parameter %}

{% api-method-parameter name="ordering" type="string" required=false %}
좋아요 많은순: -like\_users   
좋아요 적은순: like\_users
{% endapi-method-parameter %}

{% api-method-parameter name="user\_\_generation" type="integer" %}
10대 이하 : 1   
20대 : 2   
30대 : 3   
40대 : 4   
50대 이상 : 5
{% endapi-method-parameter %}

{% api-method-parameter name="user\_\_gender" type="string" %}
남성 : m   
여성 : f
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
리스트 출.
{% endapi-method-response-example-description %}

```javascript
{
    "count": 7,
    "next": "http://localhost:8000/api/items/?page=2",
    "previous": null,
    "results": [
        {
            "id": 7,
            "user": {
                "email": "swkang@fastcampus.co.kr"
            },
            "public_visibility": true,
            "like_users": [],
            "category": "디지털/가전제품",
            "is_purchase": false,
            "purchase_date": null,
            "created_time": "2018-06-19T12:02:52.328046",
            "modified_time": "2018-06-19T12:02:52.330643",
            "name": "카도 미니 가시광촉매 차량용 공기청정기 실버",
            "purchase_url": "https://www.coupang.com/vp/products/29576028",
            "price": 253920,
            "img": "http://localhost:8000/media/items/6bf2c6f5-90c6-4d47-81fa-71e7c4ed4ad3.jpeg"
        },
        {
            "id": 6,
            "user": {
                "email": "swkang@fastcampus.co.kr"
            },
            "public_visibility": true,
            "like_users": [],
            "category": "기타",
            "is_purchase": false,
            "purchase_date": null,
            "created_time": "2018-06-19T12:02:36.235813",
            "modified_time": "2018-06-19T12:02:36.238361",
            "name": "ESR 뉴아이패드 6세대 2018 스마트커버 케이스",
            "purchase_url": "http://naver.me/GiQ5EWa7",
            "price": 25900,
            "img": "http://localhost:8000/media/items/9596208268224416_263489014.jpeg"
        },
        {
            "id": 5,
            "user": {
                "email": "swkang@fastcampus.co.kr"
            },
            "public_visibility": true,
            "like_users": [],
            "category": "기타",
            "is_purchase": false,
            "purchase_date": null,
            "created_time": "2018-06-19T12:02:17.918448",
            "modified_time": "2018-06-19T12:02:17.922059",
            "name": "2017 뉴아이패드 9.7 필름 강화유리 5세대",
            "purchase_url": "http://itempage3.auction.co.kr/DetailView.aspx?ItemNo=B527111076",
            "price": 11500,
            "img": "http://localhost:8000/media/items/15234081e6.jpeg"
        },
        {
            "id": 4,
            "user": {
                "email": "swkang@fastcampus.co.kr"
            },
            "public_visibility": true,
            "like_users": [],
            "category": "디지털/가전제품",
            "is_purchase": false,
            "purchase_date": null,
            "created_time": "2018-06-19T12:01:41.667941",
            "modified_time": "2018-06-19T12:01:41.669967",
            "name": "애플 에어팟 블루투스이어폰 AirPods",
            "purchase_url": "http://shopping.interpark.com/product/productInfo.do?prdNo=5565493696",
            "price": 195130,
            "img": "http://localhost:8000/media/items/5565493696_l_tlFAZoO.jpeg"
        },
        {
            "id": 3,
            "user": {
                "email": "swkang@fastcampus.co.kr"
            },
            "public_visibility": true,
            "like_users": [],
            "category": "디지털/가전제품",
            "is_purchase": false,
            "purchase_date": null,
            "created_time": "2018-06-19T12:01:20.108318",
            "modified_time": "2018-06-19T12:01:20.112680",
            "name": "Apple 공인판매점 MacBook Pro [MPXY2KH/A] 13형 512G",
            "purchase_url": "http://www.11st.co.kr/product/SellerProductDetail.tmall?method=getSellerProductDetail&prdNo=1780658921",
            "price": 2425000,
            "img": "http://localhost:8000/media/items/1780658921_B_7qe0lBx.jpeg"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://zirmi.com" path="/api/items/" %}
{% api-method-summary %}
Create
{% endapi-method-summary %}

{% api-method-description %}
 아이템 생성을 위한 API 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



