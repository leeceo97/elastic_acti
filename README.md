Elasticsearch
https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html
- Docker로 빌드
- Django-elastic 연동과정
    - Api 리스트
        - GET elastic apm 조회
        - POST json 형식으로 데이터 업로드
            - 최대 길이 확인하기
- $ curl -XPOST "http://localhost:9200/_bulk" -H 'Content-Type: application/json' --data-binary @bulk.json


{
  "query": {
    "bool": {
      "should": [
        {
          "match": {
            "pre_manufacture": {
              "query": "동장              ",
              "fuzziness": "AUTO"
            }
          }
        }
      ],
      "minimum_should_match": 1
    }
  }
}

쿼리문 예시
