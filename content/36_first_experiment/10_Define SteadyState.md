+++
title = "2.1 정상 상태 정의"
chapter = true
weight = 10
+++

# 2.1 정상 상태 정의

실패 생성을 시작하기 전에 시작점은 애플리케이션의 안정된 상태를 이해하는 것입니다. 여기에는 사용자 경험의 유효성을 검사하고 시스템이 정상적인 조건에서 작동하는지 이해하기 위해 대시 보드 및 메트릭 수정이 포함됩니다.

우리 연구실에서는 Sock Shop 애플리케이션을 선택했습니다. [Sock Shop](https://github.com/microservices-demo/microservices-demo)은 [Weaveworks](https://weave.works)가 데모 및 테스트 목적으로 처음 개발한 마이크로 서비스 샘플 애플리케이션 입니다. 그들은 그것을 오픈 소스로 만들어 다른 조직에서 학습 및 데모 목적으로 사용할 수 있도록 했습니다.


![sockshop](https://github.com/microservices-demo/microservices-demo.github.io/raw/master/assets/sockshop-frontend.png)

## Shop Sock 아키텍처

데모 마이크로 서비스 애플리케이션의 아키텍처는 가능한 한 많은 마이크로 서비스를 제공하도록 의도적으로 설계되었습니다. Sock Shop 애플리케이션을 잘 설계된 마이크로 서비스 애플리케이션의 모델로 사용하지 마십시오. 데모용으로 구축되었습니다. 자신만의 마이크로 서비스 기반 클라우드 네이티브 애플리케이션 설계를 막 시작한 경우 [Weaveworks](https://www.weave.works/contact/)에서 사용 사례에 맞는 올바른 아키텍처를 추천 해드립니다.

아키텍처 다이어그램에서 이러한 모든 서비스가 서로 어떻게 통신하는지 볼 수 있습니다.
![sockshop-topology](/images/sockshop-topology.png)


## 사용자 경험
계속해서 Sock Shop 애플리케이션을 살펴 보겠습니다.
시도 할 몇 가지 :

+ 아래 자격 증명을 사용하여 등록하고 로그인하십시오 (보안이 매우 안전하므로 공유하지 마십시오).
    - **Username:** `user`	
    - **Password:** `password`
+ 다양한 아이템보기
+ 장바구니에 항목 추가
+ 장바구니에서 항목 제거
+ 항목 확인


이것은 우리가 실험을 할 때 사용자 경험을 비교하고자 하는 애플리케이션의 안정된 상태입니다.
