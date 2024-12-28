---
title: Migrating legacy lab environment
---

# Migrating legacy lab environment

2023년 7월 21일, EKS 워크숍의 인프라 프로비저닝 방식에 크게 변화가 있었습니다. 이전에는 워크숍이 시작하기 전에 모든 인프라를 프로비저닝하기 위해 Terraform을 사용했었습니다. 초기 시작 시 발생할 수 있는 문제를 줄이기 위해 변경하기로 결정되었습니다. 이제 워크숍 인프라는 점진적으로 구축되며, 초기 설정이 단순화되었습니다.

If you have a lab environment that was provisioned via the legacy mechanism based on Terraform you will need to migrate to this new provisioning mechanism. The steps below provide a guide to clean up your existing environment.

First, access the Cloud9 IDE and run the following to clean up the sample application running in the cluster. This is necessary to ensure Terraform can clean up the EKS cluster and VPC:

```bash
$ delete-environment
```

Next you should delete the AWS resources that were provisioned by Terraform. From the Git repository you initially cloned (for example on your local machine) run the following commands:

```bash
$ cd terraform
$ terraform destroy -target=module.cluster.module.eks_blueprints_kubernetes_addons --auto-approve
# To delete the descheduler add-on, run the following command:
$ terraform destroy -target=module.cluster.module.descheduler --auto-approve
# To delete the core blueprints add-ons, run the following command:
$ terraform destroy -target=module.cluster.module.eks_blueprints --auto-approve
# To delete the remaining resources created by Terraform, run the following command:
$ terraform destroy --auto-approve
```

You can now create a new lab environment following the steps [outlined here](../../../../docs/introduction/setup/your-account/).
