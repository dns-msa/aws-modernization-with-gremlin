+++
title = "컨테이너 도구 설정"
chapter = true
weight = 20
+++

# 필요한 모든 도구 및 권한 설정

이 workshop 모듈을 완료하려면 먼저 eksctl을 설치해야 합니다. 이를 위한 안내는 [eksctl.io](https://eksctl.io/introduction/#installation)에서 확인할 수 있습니다. eksctl("eks control" 이라고 발음)은 EKS에서 클러스터를 생성하기 위한 간단한 CLI 도구입니다. Go로 작성되고 CloudFormation을 사용하며 [Weaveworks](https://weave.works)에서 생성했으며 커뮤니티의 기여를 환영합니다.

{{% notice warning %}}
자체 AWS 계정을 사용하는 경우 구성 규칙을 구성하고 에이전트를 설치하려면 EKS 클러스터를 생성할 수 있는 권한과 EKS 클러스터 내에서 관리자 권한이 필요합니다. 테넌트에서 이 작업을 수행할 수 있는 권한이 조직 내에 있는지 확인하십시오.
{{% /notice %}}

