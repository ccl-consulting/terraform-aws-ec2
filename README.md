[![CircleCI](https://circleci.com/gh/ccl-consulting/terraform-aws-ec2.svg?style=svg)](https://circleci.com/gh/ccl-consulting/terraform-aws-ec2)

# Terraform AWS Europe

## Init

> The Devops Team use this terraform plan for demonstration

This demonstrates the provisioning of a single compute VM(`t2.micro = 1vCPU / 1 Go `) in Amazon Web Service

```bash
$ terraform init
```

This will create the `terraform.tfstate` file

## Running it

```bash
$ terraform validate -var 'aws_access_key=$AWS_ACCESS_KEY' -var 'aws_secret_key=$AWS_SECRET_KEY' -var 'aws_region=eu-west-3'
$ terraform plan -var 'aws_access_key=$AWS_ACCESS_KEY' -var 'aws_secret_key=$AWS_SECRET_KEY' -var 'aws_region=eu-west-3'
$ terraform apply -var 'aws_access_key=$AWS_ACCESS_KEY' -var 'aws_secret_key=$AWS_SECRET_KEY' -var 'aws_region=eu-west-3'
```

## Variable

| Variable       | Value - Sample  | Description         |
| -------------- | --------------- | ------------------- |
| aws_access_key | $AWS_ACCESS_KEY | Your AWS Access Key |
| aws_secret_key | $AWS_SECRET_KEY | Your AWS Secret Key |
| aws_region     | eu-west-3       | AWS Region - Paris  |


## Appendix

### Use on Free Tier

| Family            | Type      | vCPUs | Memory (GiB) | Instance Storage (GB) | EBS-Optimized Available | Network Performance | IPv6 Support |
| ----------------- | --------- | ----- | ------------ | --------------------- | ----------------------- | ------------------- | ------------ |
| General purpose   | t2.micro  | 1     | 1            | EBS only              | -                       | Low to Moderate     | Yes          |

### Use a standard account

| Family            | Type      | vCPUs | Memory (GiB) | Instance Storage (GB) | EBS-Optimized Available | Network Performance | IPv6 Support |
| ----------------- | --------- | ----- | ------------ | --------------------- | ----------------------- | ------------------- | ------------ |
| Compute optimized | c5.large  | 2     | 4            | EBS only              | Yes                     | Up to 10 Gigabit    | Yes          |
| General purpose   | t2.medium | 2     | 4            | EBS only              | -                       | Low to Moderate     | Yes          |
| General purpose   | t2.micro  | 1     | 1            | EBS only              | -                       | Low to Moderate     | Yes          |

### AWS Region

| Zone      | Region  |
| --------- | ------- |
| eu-west-1 | Ireland |
| eu-west-3 | Paris   |

### Supported Operating System - AWS AMI

| OS                   | AMI ID                |
| -------------------- | --------------------- |
| CentOS 7             |                       |
| Ubuntu 14            |                       |
| Fedora Cloud Base 29 | ami-0ee503641c4f61ba6 |


Fedora-Cloud-Base-29-1.2.x86_64-hvm-eu-west-3-standard-0 - ami-0ee503641c4f61ba6
