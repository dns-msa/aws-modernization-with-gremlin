+++
title = "2.6 작업 항목 검증"
chapter = true
weight = 60
+++

# 2.6 작업 항목 검증
자동 확장을 설정하여 애플리케이션의 탄력성을 높였습니다. 다음과 같이 보일 것입니다.
![AWS Scaling policies](/images/aws_scaling_policies.png)


예상 한대로 작동하는지 확인해 보겠습니다. 이전에 했던 것처럼 다음 단계로 이동하기 전에 가설 및 중단 조건을 적어 두어야 합니다. 필요한 경우 실험 카드를 자유롭게 사용하십시오.

![Experiment Card](/images/Experiment_Card.jpg)

[Gremlin](app.gremlin.com)으로 돌아가서 모든 호스트에 CPU 공격을 구성해 보겠습니다. **"Attacks"**을 클릭하면 왼쪽 탐색 표시 줄에서 **"New Attack"**이 표시됩니다.

**"Attacks"**를 클릭하면 왼쪽 탐색바에서 **"New Attack"**이 표시됩니다.

![Gremlin UI New Attack](/images/gremlin/gremlin_ui_create_new_attack.png)

**"What do you want to attack?"**에서 **Hosts**를 선택한 다음 세 개의 호스트를 선택합니다.

![Gremlin UI Select Hosts](/images/gremlin/gremlin_ui_select_hosts.png)

**"Choose a Gremlin"**에서 **"Resource"** 다음에 **"CPU"**를 선택하여 대상에서 CPU를 사용합니다. 구성의 경우 **Length**를 360 초로 변경하고 **CPU Capacity** 를 **`80`**으로 변경하고 드롭 다운에서 **"All Cores"**를 선택합니다.


![Gremlin UI CPU Attack](/images/gremlin/gremlin_ui_cpu_attack.png)

그런 다음, **"Unleash Gremlin"**을 클릭합니다.

## 관찰

> **CloudWatch 및 Container Insights에서 처음으로 CPU 실험을 실행할 때와 다른 결과가 있습니까? 노드 수에 대한 그래프가 증가했습니까?**