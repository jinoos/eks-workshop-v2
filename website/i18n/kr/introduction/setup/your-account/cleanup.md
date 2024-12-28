# Cleaning up

:::caution

Make sure you have run the respective clean up instructions for the mechanism you used to provision the lab EKS cluster before proceeding.

* [eksctl](using-eksctl/)
* [Terraform](using-terraform/)

:::

This section outlines how to clean up the IDE we've used to run the labs.

Start by opening CloudShell in the region where you deployed the CloudFormation stack:

Then run the following command to delete the CloudFormation stack:

```bash
$ aws cloudformation delete-stack --stack-name eks-workshop-ide
```
