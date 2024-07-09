![](https://img.shields.io/github/commit-activity/t/subhamay-bhattacharyya/0032-allium-cft)&nbsp;![](https://img.shields.io/github/last-commit/subhamay-bhattacharyya/0032-allium-cft)&nbsp;![](https://img.shields.io/github/release-date/subhamay-bhattacharyya/0032-allium-cft)&nbsp;![](https://img.shields.io/github/repo-size/subhamay-bhattacharyya/0032-allium-cft)&nbsp;![](https://img.shields.io/github/directory-file-count/subhamay-bhattacharyya/0032-allium-cft)&nbsp;![](https://img.shields.io/github/actions/workflow/status/subhamay-bhattacharyya/0032-allium-cft/deploy-stack.yaml)&nbsp;![](https://img.shields.io/github/issues/subhamay-bhattacharyya/0032-allium-cft)&nbsp;![](https://img.shields.io/github/languages/top/subhamay-bhattacharyya/0032-allium-cft)&nbsp;![](https://img.shields.io/github/commit-activity/m/subhamay-bhattacharyya/0032-allium-cft)&nbsp;![](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/bsubhamay/b21a193b71079cfd71034ff303e7cae9/raw/0032-allium-cft.json?)

![Preview](https://res.cloudinary.com/dcsbvxyig/image/upload/v1720444703/0032-allium/mmbqurgfrl4gru3nf1h0.jpg)

# Project Allium: Mounting an Elastic File System to multiple EC2 instances.

Creating a VPC with two public and private subnets and an EFS with mount points in the two public subets. Create two public EC2 instances in the public subnets and mounting the EFS to the two EC2 instances. This demonstrate how a EFS can be used to persist from multiple EC2 instances.

## Description

A custom **VPC** is created with two public and private subnets in two different **Availabity Zones**. An **Internet Gateway** is attached to the VPC to connect to the internet. Network Access Control List is used a first line of defence to secure the subnets. One security group (EC2 security group) controls SSH access to the EC2 instances. An EFS security group with the source security group as the EC2 security group controls access to the EFS from the EC2 instances. **Nat Gateway** grants internet access to the private subnets. An EFS created in the VPC with two mount targets in the two public subnets. Two EC2 instances are created in the two public subnets and mounts the **Elastic File System**.

![Project Allium - Design Diagram](https://res.cloudinary.com/dcsbvxyig/image/upload/v1720444703/0032-allium/mmbqurgfrl4gru3nf1h0.jpg)

### Services Used

```mermaid
mindmap
  root((CloudFormation ))
    AWS VPC
            Public and Private Subnets
            Network Access Control List
            Security Group
            Route Table
            Nat Gateway
            Internet Gateway
            VPC Gateway Endpoint for S3

   AWS Key Management Service

   AWS Elastic Filesystem

   AWS EC2 instance

   AWS IAM
```

## Root stack launching the child stacks to create the necessary resources:

![Project Allium - CloudFormation Stack](https://res.cloudinary.com/dcsbvxyig/image/upload/v1720467869/root-and-nested-stacks_xw18od.jpg)

## Security groups :

![Project Allium -  Security Groups](https://res.cloudinary.com/dcsbvxyig/image/upload/v1720467870/security-groups_isyffx.jpg)

## EC2 user data in the CloudFormation template :

![Project Allium -  User Data](https://res.cloudinary.com/dcsbvxyig/image/upload/v1720468017/ec2-user-data_k9p1k8.jpg)

## EC2 instances with EFS mounted :

![Project Allium -  Mounted EFS](https://res.cloudinary.com/dcsbvxyig/image/upload/v1720520075/ec2-with-efs_gnuuiy.jpg)

## Help

:email: Subhamay Bhattacharyya - [subhamay.aws@gmail.com]

## Authors

Contributors names and contact info

Subhamay Bhattacharyya - [subhamay.aws@gmail.com]

## Version History

- 0.1
  - Initial Release

## License

This project is licensed under Subhamay Bhattacharyya. All Rights Reserved.

## Acknowledgments
