# lw-project-docker-for-testing
Docker to setup environment for easy testing

## Introduction
로컬에서 이런 저런 테스트를 수행 할 때에, 이를 위한 환경을 갖추기 위해서는 다양한 프로그램 설치가 필요한 경우가 있다. 이때 [docker compose](https://docs.docker.com/compose/) 또는 [docker stack](https://docs.docker.com/engine/swarm/stack-deploy/)을 사용하면 환경을 빠르고 쉽게 구축 할 수 있다. 개인적으로는 서로 의존성이 있어서 반드시 같이 묶이는 경우가 아니면 테스트 환경을 빠르게 구축 하기 위해서만 사용 되는 것이 좋다고 생각한다. (사견일 뿐이니 알아서 판단하자. `docker-compose down` 이나 `docker stack rm` 을 무심코 누르고 망해본 경험이 있는 사람으로썬 추천 할 수가 없네..)

어쨌든 상황에 맞는 Compose/Stack 은 테스트를 편하게 해준다. 이 프로젝트는 내가 잘 쓰자고 만들어놓을 설정파일들 (및 실행 방법들)을 그때그때 정리 해놓기 위한 프로젝트이다. 개인의 필요성에 의해 만드는 것이므로 개인의 사용 방법에 따라 설정이 변경 될 수 있으며, 오래 사용하지 않는 경우 버전의 업데이트가 안될 수 있다.

혹시 필요한 사람은 얼마든지 가져다 써도 되고, 이상한 부분이나 의견/요청/이슈등록은 언제나 환영하며, 꼭 해결한다는 보장은 못 드리는 점 양해바란다. 또한 윈도우 환경에서 반드시 동작한다는 보장을 못한다. (나는 정신건강을 위해서 macos 나 linux 환경에서만 해본다) 이따금 급하게 하다가 윈도우 환경에서 하는 경우도 있고, 혹시 요청이 들어오면 한번 해볼지도..?

## Compose/Stack List


## [Author's Blog](https://lonelywolflee.github.io/)