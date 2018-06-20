# Search

{% api-method method="get" host="https://zirmi.com" path="/api/reviews/search/" %}
{% api-method-summary %}
Search
{% endapi-method-summary %}

{% api-method-description %}
리뷰 검색을 위한 API
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="sort" type="string" required=true %}
제목으로 검색: title  
내용으로 검색: content  
아이템명으로 검색: item  
전체 검색: all
{% endapi-method-parameter %}

{% api-method-parameter name="keyword" type="string" required=false %}
검색할 내용\(입력 안할시 전체 리스트 출력\)
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="integer" required=false %}
page 숫자(page 당 리뷰 5개)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
case1: 리뷰 검색 성공.  
case2: 검색 결과가 없을 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "_comment": "case1",
    "count": 1,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 1,
            "user": {
                "email": "rainsound128@gmail.com"
            },
            "item": 2,
            "content": "<p style=\"font-family: &quot;Apple SD Gothic Neo&quot;, &quot;Helvetica Neue&quot;, AppleGothic, &quot;맑은 고딕&quot;, 나눔고딕, 돋움; line-height: 26.35px; list-style-type: none; padding: 10px 0px; margin-bottom: 0px; text-align: justify; word-break: break-all; font-size: 17px; color: rgb(51, 51, 51);\">[IT동아 이문규 기자] 솔직히 고백하는데, 필자는 그동안 애플 맥북을 사용하는 이들을 보며, '과연 저들 중에 맥북이 진정 유용해서 쓰는 이들이 얼마나 될까?'하는 삐딱한 시선을 보냈다. ...",
            "view_count": 4,
            "created_time": "2018-06-18T14:24:41.430097",
            "modified_time": "2018-06-18T14:24:41.430126",
            "title": "맥북 후기"
        }
    ]
}


{
    "_comment": "case2",
    "detail": "검색결과가 없습니다"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
case1: sort가 없을 경우.  
case2: keyword는 있지만 sort가 title, content, item, all 중 하나가 아닐 경우.
{% endapi-method-response-example-description %}

```javascript
{
    "_comment": "case1",
    "detail": "sort를 입력해주세요"
}


{
    "_comment": "case2",
    "detail": "올바른 sort를 입력해주세요"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

