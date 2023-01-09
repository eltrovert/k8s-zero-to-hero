# Setup Kubernetes Cluster On AWS Using EKS (Elastic Container Service)

In this article, we will go over the steps for setting up a Kubernetes cluster on Amazon Web Services (AWS) using the console, shell, and CloudFormation.

## **Prerequisites**

Before setting up a Kubernetes cluster on AWS, you will need to have an AWS account and have the **`aws`** command-line tool installed on your local machine. You can sign up for an AWS account and install the **`aws`** tool by following the instructions on the AWS website: **[https://aws.amazon.com/](https://aws.amazon.com/)**.

## **Setting up a Kubernetes cluster using the console**

The easiest way to set up a Kubernetes cluster on AWS is to use the AWS console.

1. Log in to the AWS console (**[https://console.aws.amazon.com/](https://console.aws.amazon.com/)**).
2. Navigate to the Amazon Elastic Container Service for Kubernetes (EKS) page by clicking on the "Services" menu and selecting "EKS" under the "Compute" category.
3. Click on the "Create cluster" button.
4. On the "Create cluster" page, choose the desired settings for your cluster (e.g. cluster name, VPC, subnets, etc.).
5. Click on the "Create" button to create the cluster.

The process of creating the cluster may take several minutes. Once the cluster is created, you can view it in the AWS console by clicking on the "Clusters" tab in the Amazon EKS page.

## **Setting up a Kubernetes cluster using the shell**

You can also set up a Kubernetes cluster on AWS using the **`aws`** command-line tool.

To create a Kubernetes cluster using the shell, run the following command:

```bash
aws eks create-cluster --name CLUSTER_NAME --role-arn ROLE_ARN --resources-vpc-config subnetIds=SUBNET_IDS,securityGroupIds=SECURITY_GROUP_IDS
```

Replace **`CLUSTER_NAME`** with the desired name for your cluster, **`ROLE_ARN`** with the Amazon Resource Name (ARN) of the IAM role that will be used to create the cluster, and **`SUBNET_IDS`** and **`SECURITY_GROUP_IDS`** with the IDs of the VPC subnets and security groups, respectively.

You can also specify additional options for the cluster, such as the Kubernetes version and the number of worker nodes, by using the **`--version`** and **`--capacity-type`** flags, respectively. For example:

```bash
aws eks create-cluster --name CLUSTER_NAME --role-arn ROLE_ARN --resources-vpc-config subnetIds=SUBNET_IDS,securityGroupIds=SECURITY_GROUP_IDS --version 1.19 --capacity-type ON_DEMAND
```

## **Setting up a Kubernetes cluster using CloudFormation**

CloudFormation is an AWS tool that allows you to define and deploy cloud resources using configuration files. You can use CloudFormation to set up a Kubernetes cluster on AWS.

To create a Kubernetes cluster using CloudFormation, do the following:

1. Create a configuration file for your cluster. The configuration file should be written in JSON or YAML and should include the desired settings for your cluster (e.g. cluster name, VPC, subnets, etc.).

Here is an example configuration file written in YAML that creates a Kubernetes cluster with the name **`MyCluster`** in the **`us-west-2`** region:

```yaml
Resources:
  MyCluster:
    Type: AWS::EKS::Cluster
    Properties:
      Name: MyCluster
      RoleArn: ROLE_ARN
      ResourcesVpcConfig:
        SecurityGroupIds:
          - SECURITY_GROUP_ID
        SubnetIds:
          - SUBNET_ID
      Version: 1.19
```

1. Save the configuration file to your local machine.
2. Use the **`aws`** command-line tool to create a CloudFormation stack using the configuration file. Run the following command:

```
aws cloudformation create-stack --stack-name STACK_NAME --template-body FILE://CONFIG_FILE
```

Replace **`STACK_NAME`** with the desired name for your stack and **`CONFIG_FILE`** with the path to the configuration file.

The process of creating the stack may take several minutes. Once the stack is created, you can view it in the AWS console by clicking on the "CloudFormation" menu item in the "Management Tools" section.

I hope these instructions were helpful in setting up a Kubernetes cluster on AWS using the console, shell, and CloudFormation. If you have any questions or need further assistance, please don't hesitate to ask.