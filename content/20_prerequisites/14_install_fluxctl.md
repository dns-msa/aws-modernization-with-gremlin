+++
title = "fluxctl 설치"
chapter = false
weight = 14

+++

## Fluxctl 설치

[Fluxctl](https://docs.fluxcd.io/en/1.17.1/references/fluxctl.html)은 [Weave Flux](https://github.com/fluxcd/flux)와 통신 할 수있는 CLI 도구입니다.

다음 명령을 실행하여 설치하십시오.

```sh
curl -Ls https://fluxcd.io/install | sh && \
sudo mv $HOME/.fluxcd/bin/fluxctl /usr/local/bin/fluxctl
```

설치를 확인하십시오.

```sh
fluxctl version
```
