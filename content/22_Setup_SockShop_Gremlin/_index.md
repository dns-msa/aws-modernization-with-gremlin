+++
title = "Part 1: 설정"
chapter = true
weight = 22
+++

#### Shop Sock


우리 연구실에서는 Sock Shop 애플리케이션을 선택했습니다. [Sock Shop](https://github.com/microservices-demo/microservices-demo)은 [Weaveworks](https://weave.works)가 데모 및 테스트 목적으로 처음 개발한 마이크로 서비스 샘플 애플리케이션 입니다. 그들은 그것을 오픈 소스로 만들어 다른 조직에서 학습 및 데모 목적으로 사용할 수 있도록 했습니다.

![sockshop](https://github.com/microservices-demo/microservices-demo.github.io/raw/master/assets/sockshop-frontend.png)

### Shop Sock 아키텍처

데모 마이크로 서비스 애플리케이션의 아키텍처는 가능한 한 많은 마이크로 서비스를 제공하도록 의도적으로 설계되었습니다. Sock Shop 애플리케이션을 잘 설계된 마이크로 서비스 애플리케이션의 모델로 사용하지 마십시오. 데모 용으로 구축되었습니다. 자신만의 마이크로 서비스 기반 클라우드 네이티브 애플리케이션 설계를 막 시작한 경우 [Weaveworks](https://www.weave.works/contact/)에서 사용 사례에 맞는 올바른 아키텍처를 추천해드립니다.

또한 Sock Shop은 Kubernetes가 다양한 기술에서 작동하는 방식을 보여주기 위해 의도적으로 다양한 언어와 기술을 사용합니다. 다시 말하지만, 필요에 따라 새로운 기술만 고려하는 것이 좋습니다.

위 이미지에서 볼 수 있듯이 마이크로 서비스는 전자 상거래 사이트의 기능을 위해 대략적으로 정의되었습니다. 네트워크가 구성되었지만 기술 제한으로 인해 일부 배포에서는 구현되지 않을 수 있습니다.

모든 서비스는 HTTP를 통해 REST를 사용하여 통신합니다. 이것은 개발 및 테스트의 단순성 때문에 선택되었습니다. API 스펙은 개발 중입니다.

![sockshop-topology](/images/sockshop-topology.png)

{{% children showhidden="false" %}}
