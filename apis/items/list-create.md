# List, Create

{% api-method method="get" host="https://zirmi.com" path="/api/items/" %}
{% api-method-summary %}
List
{% endapi-method-summary %}

{% api-method-description %}
아이템 리스트 위한 API
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
리스트 출력.
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
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token &lt;발급 받은 토큰 key&gt;
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
아이템명
{% endapi-method-parameter %}

{% api-method-parameter name="price" type="integer" required=true %}
아이템 가격
{% endapi-method-parameter %}

{% api-method-parameter name="category" type="string" required=true %}
패션의류/잡화: a   
유아용품: b  
뷰티: c   
주방/생활용품: d   
디지털/가전제품: e   
가구/인테리어: f   
운동용품: g   
여행: h   
도서/음반/공연: i   
자동차용품: j   
기타: k
{% endapi-method-parameter %}

{% api-method-parameter name="purchase\_url" type="string" required=false %}
상품 구매 링크\(URL 형식\)
{% endapi-method-parameter %}

{% api-method-parameter name="img" type="object" required=false %}
상품 이미지\(파일 업로드\)
{% endapi-method-parameter %}

{% api-method-parameter name="public\_visibility" type="boolean" required=false %}
전체 공개 여부\(defaut=True\)
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
아이템 생성완료.
{% endapi-method-response-example-description %}

```javascript
{
    "detail": "아이템이 생성되었습니다",
    "item": {
        "id": 14,
        "user": {
            "email": "windog100@hanmail.net"
        },
        "public_visibility": true,
        "like_users": [],
        "category": "뷰티",
        "is_purchase": false,
        "purchase_date": null,
        "created_time": "2018-06-19T12:56:38.001652",
        "modified_time": "2018-06-19T12:56:38.007632",
        "name": "test3",
        "purchase_url": "http://www.11st.co.kr/product/SellerProductDetail.tmall?method=getSellerProductDetail&prdNo=1780658921",
        "price": 150000,
        "img": "/media/items/1780658921_B_AcLDuqt.jpeg"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
name or price or category가 없는 경우.  
{% endapi-method-response-example-description %}

```javascript
{
    "detail": "name, price, category를 입력해주세요"
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

