# 정리하기

:::caution

{% hint style="warning" %}
주의

진행하기 전에 실습용 EKS 클러스터를 프로비저닝하는 데 사용한 메커니즘에 대한 각각의 정리 지침을 실행했는지 확인하세요.

* [ekscli](using-eksctl.md)
* [Terraform](using-terraform.md)
{% endhint %}

이 섹션에서는 실습을 실행하는 데 사용한 IDE를 정리하는 방법을 설명합니다.

CloudFormation 스택을 배포한 리전에서 CloudShell을 열어 시작하세요:

{% embed url="https://console.aws.amazon.com/cloudshell/home" %}

그런 다음 다음 명령을 실행하여 CloudFormation 스택을 삭제하세요:

```bash
$ aws cloudformation delete-stack --stack-name eks-workshop-ide
```
