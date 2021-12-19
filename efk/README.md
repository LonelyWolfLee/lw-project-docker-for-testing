# EFK (Elasticsearch + Fluentd + Kibana)
보통 모니터링 시스템이나 중앙집중형 로그 시스템을 구축 하는 경우 ELK(Elasticsearch + Logstash + Kibana) stack 을 많이 사용 할 것이다. 참 좋고 자료도 많고 한데, Logstash 가 메모리를 어지간히 먹어야 말이지... 그래서 나는 [Fluentd][1], [FluentBit][2]를 사용하하여 환경을 구축하는데에 관심을 가지고 사용 사례를 연구하고 있다. 이 중에 중앙 집중형 Log Aggregator 역할로는 `Fluentd` 를 사용하는 것을 선호한다. 그래서 간단하게 EFK 를 사용한 Log Aggregation 을 할 수 있는 환경을 구성해보겠다.

## Prerequisites
- Docker 는 알아서 설치한다
- 참고자료 `Fluentd 의 EFK 가이드`에 따라 [fluent-plugin-elasticsearch][4] 가 설치된 fluentd 이미지를 준비한다
- Docker Engine 의 RAM 은 3GB 이상으로 설정 할 것을 권장한다

## Requirements
- Log Aggregation 은 Fluentd 를 사용하며 input source 는 [forward][3] 방식으로 24224 port 를 사용한다.
- Fluentd의 tag가 log 로 시작하는 경우만 처리한다.
- 들어오는 로그는 json 형태로 제한한다.
- `nested_log`가 있는 경우 각 필드를 한단계 위의 필드로 이동시킨다.
- 중간에 Elasticsearch 에 장애가 생기더라도 file 에 일정 수준 저장 할 수 있도록 file buffer 를 설정한다.

## How to run
```bash
docker-compose up --detach
```

## References
- [Elastic 공식 홈페이지 가이드](https://www.elastic.co/guide/en/elastic-stack-get-started/current/get-started-docker.html)
- [https://github.com/deviantony/docker-elk](https://github.com/deviantony/docker-elk)
- [Fluentd 의 EFK 가이드](https://docs.fluentd.org/container-deployment/docker-compose)

<!-- Links -->
[1]: https://docs.fluentd.org/ "Fluentd Documentation"
[2]: https://docs.fluentbit.io/manual/ "Fluent Bit Documentation"
[3]: https://docs.fluentd.org/input/forward "Fluentd forward input"
[4]: https://github.com/uken/fluent-plugin-elasticsearch "Fluentd elasticsearch plugin"