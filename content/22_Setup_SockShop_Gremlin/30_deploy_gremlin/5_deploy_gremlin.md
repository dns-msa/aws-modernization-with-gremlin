+++
title = "1.7 Gremlin 배포"
chapter = true
weight = 07
+++

# Gremlin 배포

자격 증명을 찾고 오른쪽 상단의 **Avatar** 아이콘을 클릭 한 다음 **"Team Settings"**을 클릭합니다.

![Gremlin Navigation to Team Settings](/images/gremlin/gremlin_people_team.png)

“Configuration”탭을 선택합니다.


터미널로 돌아가 Gremlin Helm 차트에 대한 리포지토리를 추가하여 시작합니다.
```
helm repo add gremlin https://helm.gremlin.com

```

**이 워크샵을 직접 실행하는 경우**, Gremlin Kubernetes 클라이언트용 네임 스페이스를 만듭니다.

```
kubectl create namespace gremlin
```

다음으로 `helm` 명령을 실행하여 Gremlin 클라이언트를 설치합니다. 이 명령에는 실제 데이터로 대체해야 하는 세 개의 자리 표시자 변수가 있습니다. `$GREMLIN_TEAM_ID`를 팀 ID로 바꾸고`$GREMLIN_TEAM_SECRET`도 보안 키로 바꿉니다. 또한`$GREMLIN_CLUSTER_ID`를 클러스터의 고유한 이름으로 바꾸려고 합니다.

Gremlin UI로 돌아가 `$GREMLIN_TEAM_ID` 및 `$GREMLIN_TEAM_SECRET` 를 찾아 보겠습니다.

![Gremlin Navigation to Configuration](/images/gremlin/gremlin_config.png)

**Team ID**를 복사하고 **Secret Key** 에서 **“Reset”**을 누릅니다. Key를 복사해야 합니다.


```
export GREMLIN_TEAM_ID=<GREMLIN_TEAM_ID를 넣으세요>
export GREMLIN_TEAM_SECRET=<GREMLIN_TEAM_SECRET을 넣으세요>
export GREMLIN_CLUSTER_ID=MY_GREMLIN
```


```
    helm install gremlin gremlin/gremlin \
    --namespace gremlin \
    --set gremlin.secret.managed=true \
    --set gremlin.secret.type=secret \
    --set gremlin.secret.teamID=$GREMLIN_TEAM_ID \
    --set gremlin.secret.clusterID=$GREMLIN_CLUSTER_ID \
    --set gremlin.secret.teamSecret=$GREMLIN_TEAM_SECRET
```

축하합니다! 🎉 Gremlin을 클러스터에 배포했습니다. https://app.gremlin.com/clients/infrastructure로 이동하여 Gremlin UI에서 설치를 확인하십시오.

![Gremlin Clients View](/images/gremlin/gremlin_ui_clients.png)
