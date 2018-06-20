# List, Create

{% api-method method="get" host="https://zirmi.com" path="/api/reviews/" %}
{% api-method-summary %}
List
{% endapi-method-summary %}

{% api-method-description %}
리뷰 리스트 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="page" type="integer" required=false %}
page 숫자\(page 당 아이템 5개\)
{% endapi-method-parameter %}

{% api-method-parameter name="ordering" type="string" required=false %}
뷰수 많은순: -view\_count  
뷰수 적은순: view\_count
{% endapi-method-parameter %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
리뷰 리스트 정상 출력.
{% endapi-method-response-example-description %}

```javascript
{
    "count": 2,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 2,
            "user": {
                "email": "rainsound128@gmail.com"
            },
            "item": 19,
            "content": "<p><span style=\"color: rgb(51, 51, 51); font-family: NanumBarunGothic, &quot;맑은 고딕&quot;, &quot;malgun gothic&quot;, AppleGothicNeoSD, &quot;Apple SD 산돌고딕 Neo&quot;, &quot;Microsoft NeoGothic&quot;, &quot;Droid sans&quot;, sans-serif; background-color: rgb(238, 238, 238); font-size: medium;\"><span style=\"font-size: x-large;\"><b>프로니까 프로답게.</b></span><br><span style=\"color: red;\">프로는 화면이 중요하다.</span>&nbsp;9.7형 아이패드 프로에 더해 12.9형 아이패드 프로는 화면이 스마트폰과 비교해서 훨씬 더 크고 넓으며 그만큼 손상될 가능성이 더 크다. ...",
            "view_count": 1,
            "created_time": "2018-06-19T23:25:59.651929",
            "modified_time": "2018-06-19T23:25:59.651963",
            "title": "아이패드 강화 필름 후기"
        },
        {
            "id": 1,
            "user": {
                "email": "rainsound128@gmail.com"
            },
            "item": 2,
            "content": "<p style=\"font-family: &quot;Apple SD Gothic Neo&quot;, &quot;Helvetica Neue&quot;, AppleGothic, &quot;맑은 고딕&quot;, 나눔고딕, 돋움; line-height: 26.35px; list-style-type: none; padding: 10px 0px; margin-bottom: 0px; text-align: justify; word-break: break-all; font-size: 17px; color: rgb(51, 51, 51);\">[IT동아 이문규 기자] 솔직히 고백하는데, 필자는 그동안 애플 맥북을 사용하는 이들을 보며, '과연 저들 중에 맥북이 진정 유용해서 쓰는 이들이 얼마나 될까?'하는 삐딱한 시선을 보냈다. ...",
            "view_count": 1,
            "created_time": "2018-06-18T14:24:41.430097",
            "modified_time": "2018-06-18T14:24:41.430126",
            "title": "맥북 후기"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://zirmi.com" path="/api/reviews/" %}
{% api-method-summary %}
Create
{% endapi-method-summary %}

{% api-method-description %}
리뷰 생성을 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token &lt;발급 받은 토큰 key&gt;
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="item" type="integer" required=true %}
구매 완료한 아이템 pk
{% endapi-method-parameter %}

{% api-method-parameter name="title" type="string" required=true %}
리뷰 제목
{% endapi-method-parameter %}

{% api-method-parameter name="content" type="string" required=true %}
리뷰 내용
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
리뷰 생성 성공.  
{% endapi-method-response-example-description %}

```javascript
{
    "id": 3,
    "user": {
        "email": "rainsound128@gmail.com"
    },
    "item": 19,
    "content": "정말 좋습니다",
    "view_count": 0,
    "created_time": "2018-06-20T10:04:03.156964",
    "modified_time": "2018-06-20T10:04:03.157074",
    "title": "19 후기"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
case1: item or title or content가 없는 경우.    
case2: 구매 완료한 아이템 pk가 아닌 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "_comment": "case1",
    "item": [
        "이 필드는 필수 항목입니다."
    ],
    "content": [
        "이 필드는 필수 항목입니다."
    ],
    "title": [
        "이 필드는 필수 항목입니다."
    ]
}


{
    "_comment": "case2",
    "item": [
        "유효하지 않은 pk \"193\" - 객체가 존재하지 않습니다."
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
