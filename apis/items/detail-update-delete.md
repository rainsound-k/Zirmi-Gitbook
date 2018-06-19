# Detail, Update, Delete

{% api-method method="get" host="https://zirmi.com" path="/api/items/<item\_pk>/" %}
{% api-method-summary %}
Detail
{% endapi-method-summary %}

{% api-method-description %}
아이템 상세 정보를 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="item\_pk" type="integer" required=true %}
item pk 값
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
아이템 detail 정상 출력.
{% endapi-method-response-example-description %}

```javascript
{
    "id": 7,
    "user": {
        "email": "rainsound128@gmail.com"
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
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://zirmi.com" path="/api/items/<item\_pk>/" %}
{% api-method-summary %}
Update
{% endapi-method-summary %}

{% api-method-description %}
아이템 업데이트를 위한 API
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
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "id": 15,
    "user": {
        "email": "rainsound128@gmail.com"
    },
    "public_visibility": true,
    "like_users": [],
    "category": "f",
    "is_purchase": false,
    "purchase_date": null,
    "created_time": "2018-06-19T13:15:33.537241",
    "modified_time": "2018-06-19T15:28:40.469171",
    "name": "에어팟",
    "purchase_url": "http://www.11st.co.kr/product/SellerProductDetail.tmall?method=getSellerProductDetail&prdNo=1780658921",
    "price": 200000,
    "img": "http://localhost:8000/media/items/1780658921_B_2FT9KVS.jpeg"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
name or price or category가 없는 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "category": [
        "이 필드는 필수 항목입니다."
    ],
    "name": [
        "이 필드는 필수 항목입니다."
    ],
    "price": [
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
아이템 user가 아닐 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "detail": "이 작업을 수행할 권한(permission)이 없습니다."
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

{% api-method method="delete" host="https://zirmi.com" path="/api/items/<item\_pk>/" %}
{% api-method-summary %}
Delete
{% endapi-method-summary %}

{% api-method-description %}
아이템 삭제를 위한 API
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
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}

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
아이템의 user가 아닐 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "detail": "이 작업을 수행할 권한(permission)이 없습니다."
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

