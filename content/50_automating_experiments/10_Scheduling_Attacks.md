+++
title = "4.1 스케줄링"
chapter = true
weight = 10
+++

# 4.1 스케줄링
## Gremlin 공격 예약

우리는 자동화의 첫 단계를 밟을 것입니다! Gremlin을 사용하면 특정 요일 및 지정된 시간에 실행되도록 공격을 예약 할 수 있습니다. 일정이 생성할 수 있는 최대 공격 수를 설정할 수도 있습니다.


[Gremlin](https://app.gremlin.com)으로 돌아가서 Shutdown 공격을 구성하는 것으로 시작하겠습니다.

왼쪽 탐색 표시 줄에서 **"New Attack"** 다음에 나오는 **"Attacks"**을 클릭합니다.

![Gremlin UI New Attack](/images/gremlin_ui_create_new__blackhole_attack.png)

**"What do you want to attack?"**에서 **Containers**를 선택한 다음 **"Tags"** 보기로 전환 할 수 있습니다.

![Gremlin UI - Containers - Tags](/images/gremlin_ui_containers_tags.png)

그런 다음, **Target all containers**을 전환하고 **Number of targets to impact** 를 **`1`**로 변경합니다.

![Gremlin UI - Containers - 1](/images/gremlin_ui_containers_tags_target_1.png)


이것은 무작위로 컨테이너 1 개를 대상으로 합니다.

**"Choose a Gremlin"**에서 **"State"**를 선택한 다음 **"Shutdown"**을 선택합니다. **Delay**을 **`0`**으로 변경하고 **Reboot**을 끕니다.

![Gremlin UI shutdown Attack](/images/gremlin_ui_shutdown_config.png) 

이제 공격을 예약 할 수 있습니다. **Schedule for later**을 켜고 **Randomly within a time frame**를 선택하고 월요일, 수요일 및 금요일을 선택합니다.
**Runs per day**에 **3**을 입력합니다.
**`09:00` 과 `15:00`** 근무 시간 사이에 실행하려고 합니다.

예약하려면 **Unleash Gremlin** 버튼을 누르세요.

![Gremlin UI schedule attack](/images/gremlin_ui_schedule_attack.png) 

Gremlin UI의 **"Schedules"**를 통해 예약된 모든 공격을 볼 수 있습니다.
![Gremlin UI scheduled attacks](/images/gremlin_ui_schedules.png) 
