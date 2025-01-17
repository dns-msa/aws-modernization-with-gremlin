+++
title = "Part 4: 카오스 엔지니어링 자동화"
chapter = true
weight = 50
+++

# Part 4: 카오스 엔지니어링 자동화

## 카오스 엔지니어링 자동화란?
**카오스 엔지니어링 자동화란**은 **지속적인** 방식으로 카오스 엔지니어링 실험을 구현하여 **과거 실패로의 회귀를 방지하는 방법입니다.**

## 자동화해야 하는 이유

실험 자동화는 이러한 장애에 대해 지속적으로 애플리케이션을 설계해야 하기 때문에 애플리케이션이 장애에 취약하지 않다는 것을 입증합니다. 이는 애플리케이션 개발자가 애플리케이션을 구축할 때 일반적이고 알려진 오류를 먼저 생각하도록 하는 강제 기능입니다.

프로덕션 환경에서 실험을 자동화하기 전에 사전 제작 환경에서 실험을 자동화하려고 합니다.

Gremlin을 사용하면 자동화를 다양한 방법으로 구현할 수 있습니다.

+ 일정
+ API 호출
+ SDK 구현
+ 상태 확인
+ CI/CD



{{% children showhidden="false" %}}
