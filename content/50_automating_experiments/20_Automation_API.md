+++
title = "4.2 API"
chapter = true
weight = 20
+++

# 4.2 API
## API를 통해 Gremlin 공격 자동화

우리는 자동화의 다음 단계를 밟을 것입니다! Gremlin을 사용하면 UI와 동일한 작업을 수행하는 API를 활용할 수 있습니다. 새 공격을 생성한 후 공격을 시작하기 전에 **Gremlin API Examples**를 선택합니다. Gremlin은 첫 번째 API 공격을 실행하는데 필요한 모든 것을 제공합니다.

![Gremlin UI - Gremlin API Examples ](/images/gremlin_ui_api_examples.png) 

인증 방법을 쉽게 선택하고 적절한 CURL 명령을 받을 수 있습니다. API 토큰을 만들 수 있지만 지금은 제공된 Bearer 토큰만 사용합니다.
![Gremlin UI - Gremlin API Examples ](/images/gremlin_ui_api_examples2.png) 

계속해서 **CURL Example**를 복사하여 콘솔에 붙여 넣습니다.

CPU 실험을 실행 중이므로 다음과 같이 보입니다.
```
curl -i -X POST 'https://api.gremlin.com/v1/attacks/new?teamId=ed09d800-018a-591a-b591-75cb717a3eb5' -H 'Content-Type: application/json;charset=utf-8' -H 'Authorization: Bearer Yy1kNWJhMWMyNy05OGVlLTU2ZWUtOWUwZS00OTY5NzA1ZGUyOWI6YW5hKzEyQG******************' -d '{"target":{"hosts":{"ids":["ip-10-0-48-196.ec2.internal"]},"type":"Exact"},"command":{"type":"shutdown","commandType":"Shutdown","args":["-d","0"]}}'
```
![AWS EC2 Console - Run Attack ](/images/gremlin_ui_api_aws_console.png) 

Gremlin UI에서 API 공격이 실행되고 있음을 확인할 수 있습니다.

![Gremlin UI - Gremlin API - Attack Pending](/images/gremlin_ui_api_attack_unleashed.png) 
[문서](https://www.gremlin.com/docs/api-reference/overview/)를 통해 Gremlin의 API에 대해 자세히 읽을 수 있으며 [대화형 Swagger 문서](https://app.gremlin.com/api)에 로그인 할 수 있습니다.

Gremlin의 API를 CI/CD 파이프 라인 또는 기타 도구에 활용할 수 있습니다.