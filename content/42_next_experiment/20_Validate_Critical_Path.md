+++
title = "3.2 중요 경로 검증"
chapter = true
weight = 20
+++

# 3.2 중요 경로 검증
## 두 번째 실험
두 번째로 진행할 실험은 **중요한 애플리케이션에 문제가 있을때 애플리케이션은 어떻게 되나요?**


다음 단계로 이동하기 전에 가설 및 중단 조건을 기록하고 싶습니다.
가설은 카오스를 진행할 때 시스템에 일어날 것으로 예상되는 일을 기반으로 해야하며, 중단 조건은 실험을 중단하게 만드는 조건을 포함합니다. 필요한 경우 실험 카드를 다시 참조하세요.


![Experiment Card](/images/Experiment_Card.jpg)

## 실험 
먼저 [Gremlin](https://app.gremlin.com)으로 돌아가 중요한 경로에있는 서비스 중 하나에 **Blackhole** 공격을 구성합니다. Gremlin Blackhole 공격은 일치하는 모든 네트워크 트래픽을 삭제하므로 서비스 중단을 복제 할 수 있습니다.

왼쪽 탐색 표시 줄에서 **"New Attack"** 다음에 나오는 **"Attacks"**을 클릭합니다.

![Gremlin UI New Attack](/images/gremlin_ui_create_new__blackhole_attack.png)


**"What do you want to attack?"**에서 **Containers**를 선택한 다음 텍스트를 입력하여 아웃 서비스를 기반으로 태그를 찾습니다. **`catalogue`** 및 **`catalogue-db`**로 이동하는 두 가지 서비스를 찾습니다.

입력하고 검색 할 때 다음과 같이 표시됩니다.
![Gremlin UI - Search Tags ](/images/gremlin_ui_select_container_tags.png)

두 태그를 모두 입력 한 후 다음과 같은 두 서비스를 모두 선택합니다.
![Gremlin UI Selected Tags](/images/gremlin_ui_selected_catalogue.png)

이 실험의 적용 범위가 작고 컨테이너 2 개만 있음을 알 수 있습니다.

**"Choose a Gremlin"**에서 **"Network"** 다음에 **"Blackhole"**을 선택합니다.
![Gremlin UI Blackhole Attack](/images/gremlin_ui_network_blackhole.png) 

구성을 위해 **Length**를 **`360`** 초로 변경하고 모든 것을 그대로 둡니다.


![Gremlin UI Blackhole Attack](/images/gremlin_ui_blackhole_attack.png)


그런 다음 **"Unleash Gremlin"**을 클릭합니다.

이제 사용자 경험과 Container Insights를 통해 방금 공개한 카오스 엔지니어링 실험을 살펴 보겠습니다.

