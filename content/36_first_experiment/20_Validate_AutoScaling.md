+++
title = "2.3 Auto-Scaling 검증"
chapter = true
weight = 20
+++

# 2.3 Auto-Scaling 검증
## 실험 계획
실행할 첫 번째 시나리오는 자동 확장을 확인하고 조정하는 것입니다. AWS의 Auto-Scaling은 사용하기 쉽지만 트래픽 수요에 따라 인프라를 확장하는 수단이기 때문에 마스터하기는 어렵습니다.

카오스 엔지니어링 실험을 할 때 과학적 방법을 따르는 것에 대해 이야기 했습니다. 아래 실험 카드는 실험을 구축하는데 도움이 됩니다.

![Experiment Card](/images/Experiment_Card.jpg)

다음 단계로 이동하기 전에 **Hypothesis** 및 **Abort Conditions**을 기록하고 싶습니다. **Hypothesis**은 혼돈을 일으킬 때 시스템에 발생할 것으로 예상되는 상황을 기반으로 해야하며 **Abort Conditions**은 실험을 중단 할 수있는 조건을 포함합니다.

다음은 실험 카드의 예입니다.
![Experiment Card Example](/images/Experiment_Card_Example.jpg)

## 실험 개시
먼저 [Gremlin](https://app.gremlin.com)으로 돌아가 모든 호스트에 CPU 공격을 구성합니다.

웹 콘솔의 왼쪽 탐색 메뉴 표시 줄에서 **"Attacks"** 를 선택하면 다음에 나오는 **"New Attack"** 버튼을 클릭합니다.

![Gremlin UI New Attack](/images/gremlin/gremlin_ui_create_new_attack.png)

**"What do you want to attack?"**에서 Services 옆에 있는 **Infrastructure**를 선택한 다음 두 개의 호스트를 선택합니다.


![Gremlin UI Select Hosts](/images/gremlin/gremlin_ui_select_hosts.png)

**"Choose a Gremlin"**에서 **"Resource"** 다음에 **"CPU"**를 선택하여 대상에서 CPU를 사용합니다. 구성의 경우 **Length**를 360 초로 변경하고 **CPU Capacity** 를 **`80`**로 변경한 다음 드롭 다운에서 **"All Cores"**를 선택합니다.

![Gremlin UI CPU Attack](/images/gremlin/gremlin_ui_cpu_attack.png)

그런 다음 **"Unleash Gremlin"**을 클릭합니다.

🎉 축하합니다. 첫 번째 공격을 시작했습니다!
다음 페이지에서는 방금 공개한 카오스 엔지니어링 실험을 관찰하는 방법에 대해 설명합니다.