+++
title = "eksctl 설치"
chapter = false
weight = 11

+++

이 workshop에서는 [eksctl](https://eksctl.io/introduction/#installation)을 사용합니다. eksctl을 설치하면 시작할 준비가 된 것입니다.

터미널 명령 프롬프트에서 다음 두 명령을 입력합니다.

```
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
```

```
sudo mv /tmp/eksctl /usr/local/bin
```

**Cloud9** 환경에 `eksctl` 이 설치됩니다. 명령이 제대로 설치되었는지 테스트하려면 다음 명령을 실행하십시오.


```
eksctl get cluster
```

"No clusters found" 메시지가 표시되어야 합니다.

```
eksctl version
```

현재 workshops에서는 `eksctl` **0.19-rc.1** 이상을 사용합니다. 일부 기능은 `eksctl` 의 **0.19** 이상 버전에서만 사용할 수 있으므로 버전을 확인하세요. (2021-06-12, 현재 최신 버전은 0.53.0 입니다.)