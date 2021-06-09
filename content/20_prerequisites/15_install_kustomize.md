+++
title = "kustomize 설치"
chapter = false
weight = 15

+++

## Kustomize 설치

[Kustomize](https://github.com/kubernetes-sigs/kustomize)를 사용하면 템플릿이 없는 원시 YAML 파일을 여러 용도로 맞춤 설정할 수 있으며 원본 YAML은 그대로 두고 사용할 수 있습니다.

Linux 용 kustomize를 설치하십시오.

```sh
curl --silent --location --remote-name \
"https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize/v3.2.3/kustomize_kustomize.v3.2.3_linux_amd64" && \
chmod a+x kustomize_kustomize.v3.2.3_linux_amd64 && \
sudo mv kustomize_kustomize.v3.2.3_linux_amd64 /usr/local/bin/kustomize
```

설치를 확인하십시오.

```sh
kustomize version
```
