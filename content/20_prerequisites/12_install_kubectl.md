+++
title = "kubectl 설치"
chapter = false
weight = 12

+++

Kubernetes 명령줄 도구 [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux)를 사용하면 Kubernetes 클러스터에 대해 명령을 실행할 수 있습니다. kubectl을 사용하여 애플리케이션을 배포하고, 클러스터 리소스를 검사 및 관리하고, 로그를 볼 수 있습니다.

터미널 명령 프롬프트에서 다음 두 명령을 입력합니다.

```
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
```

```
chmod +x ./kubectl
```

```
sudo mv ./kubectl /usr/local/bin/kubectl
```


**Cloud9** 환경에 `kubectl` 이 설치됩니다. 명령이 제대로 설치되었는지 테스트하려면 다음 명령을 실행하십시오.

```
kubectl version --client
```

`kubectl` 버전 메시지가 표시되어야 합니다.

