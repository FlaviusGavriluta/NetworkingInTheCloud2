# Networking in the Cloud 2

## Story

You are managing an organization with multiple departments (dev/sales/marketing). Each department would require its own isolatad environment with a few exceptions (E.g. sales would need access to marketing and vice versa). You are given the task of designing the networking architecture, so go ahead create the VPCs and their subnet and start peering or create a Transit Gateway.

## What are you going to learn?

- What is a shared VPC in AWS.
- How to create a peering connection in AWS.
- How to create a Transit Gateway in AWS.
- How to attach VPCs to a TGW in AWS.

## Tasks

1. 1. Create a new VPC called `europe-east` with CIDR 10.10.0.0/24.
2. Create a new VPC called `europe-west` with CIDR 10.10.1.0/24.
    - A new VPC called `europe-east` with CIDR 10.10.0.0/24 is created.
    - A new VPC called `europe-west` with CIDR 10.10.1.0/24 is created.

2. Create a new Peering connection inside VPC called `my-peering-connection`. VPC Requester should be `europe-east` and another VPC to peer with (Accepter) `europe-west`. Once the connection is created the status is `Pending` and you will need to select `Accept Request` in Actions drop-down menu.
    - A new Peering connection has been created and status set to `Active`

3. 1. Create a subnet called `europe-east-01` in `europe-east` VPC with CIDR 10.10.0.0/24.
2. Create a subnet called `europe-west-01` in `europe-west` VPC with CIDR 10.10.1.0/24.
    - A subnet called `europe-east-01` in `europe-east` VPC with CIDR 10.10.0.0/24 is created.
    - A subnet called `europe-west-01` in `europe-west` VPC with CIDR 10.10.1.0/24 is created.

4. 1. Create a new Transit Gateway called `myTGW`, the rest of the settings can be left untouched.
2. Once the status of `myTGW` becomes active, go ahead and create two new Transit Gateway Attachments as part of `myTGW` ID
2.1. Select `myTGW` ID and type VPC. Your VPC ID should be the one corresponding to `europe-west` and the same for subnet ID `europe-west-01`.
2.2. In the same way, create another attachment for `europe-east`
    - A new Transit Gateway has been created and status set to `Active`
    - Two VPCs and their subnets have been attached to a Transit Gateway

## General requirements

None

## Hints

- Peering is a one-to-one connection, whereas a Transit Gateway can have thousands of networks attached to it. 
- A VPC with no subnet cannot be attached to a trasit gateway.
- Various VPCs should be separately attached to a TGW.
- Troubleshooting section available for reference in the study materials.

## Background materials

- <i class="far fa-exclamation"></i> [VPC Peering concept](project/curriculum/materials/pages/networks/networking-in-the-cloud-2.md)
- <i class="far fa-exclamation"></i> [VPC Peering](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html)
- <i class="far fa-video"></i> [AWS Networking Fundamentals](https://www.youtube.com/watch?v=hiKPPy584Mg)
- <i class="far fa-book-open"></i> [Next generation networking with AWS](https://medium.com/slalom-technology/next-generation-networking-with-aws-transit-gateway-and-shared-vpcs-9d971d868c70)
