# Setup Kubernetes Cluster On Azure AKS ( Azure Kubernetes Service)

In this article, we will go over the steps for setting up a Kubernetes cluster on Microsoft Azure using the console, shell, and Azure Infrastructure as Code (IaC) service.

## **Prerequisites**

Before setting up a Kubernetes cluster on Azure, you will need to have an Azure account and have the **`az`** command-line tool installed on your local machine. You can sign up for an Azure account and install the **`az`** tool by following the instructions on the Azure website: **[https://azure.microsoft.com/](https://azure.microsoft.com/)**.

## **Setting up a Kubernetes cluster using the Azure portal**

The easiest way to set up a Kubernetes cluster on Azure is to use the Azure portal.

1. Log in to the Azure portal (**[https://portal.azure.com/](https://portal.azure.com/)**).
2. Click on the "Create a resource" button in the top-left corner of the screen.
3. In the "Search the Marketplace" field, search for "Kubernetes service" and select the "Kubernetes service" item from the search results.
4. Click on the "Create" button.
5. On the "Create Kubernetes service" page, choose the desired settings for your cluster (e.g. resource group, region, node count, etc.).
6. Click on the "Create" button to create the cluster.

The process of creating the cluster may take several minutes. Once the cluster is created, you can view it in the Azure portal by clicking on the "Kubernetes services" item in the "All resources" list.

## **Setting up a Kubernetes cluster using the `az` command-line tool**

You can also set up a Kubernetes cluster on Azure using the **`az`** command-line tool.

To create a Kubernetes cluster using the **`az`** tool, run the following command:

```bash
az aks create --name CLUSTER_NAME --resource-group RESOURCE_GROUP --node-count NODE_COUNT --generate-ssh-keys
```

Replace **`CLUSTER_NAME`** with the desired name for your cluster, **`RESOURCE_GROUP`** with the name of the resource group where the cluster will be created, and **`NODE_COUNT`** with the number of nodes in the cluster.

You can also specify additional options for the cluster, such as the Kubernetes version and the VM size, by using the **`--kubernetes-version`** and **`--vm-size`** flags, respectively. For example:

```bash
az aks create --name CLUSTER_NAME --resource-group RESOURCE_GROUP --node-count NODE_COUNT --kubernetes-version 1.19 --vm-size Standard_D2_v3 --generate-ssh-keys
```

## **Setting up a Kubernetes cluster using Azure Infrastructure as Code**

Azure Infrastructure as Code (IaC) is a service on Azure that allows you to define and deploy cloud resources using configuration files. You can use Azure IaC to set up a Kubernetes cluster on Azure.

To create a Kubernetes cluster using Azure IaC, do the following:

1. Create a configuration file for your cluster. The configuration file should be written in JSON or YAML and should include the desired settings for your cluster (e.g. cluster name, resource group, node count, etc.).

Here is an example configuration file written in YAML that creates a Kubernetes cluster with the name **`MyCluster`** in the **`westus2`** region:

```yaml
Resources:
  MyCluster:
    Type: Microsoft.ContainerService/managedClusters
    Properties:
      location: westus2
      properties:
        kubernetesVersion: 1.19
        agentPoolProfiles:
          - name: default
            count: 3
            vmSize: Standard_D2_v3
```

1. Save the configuration file to your local machine.
2. Use the **`az`** command-line tool to create a resource group and deploy the configuration file to it. Run the following commands:

```bash
az group create --name RESOURCE_GROUP --location LOCATION
az group deployment create --resource-group RESOURCE_GROUP --template-file CONFIG_FILE
```

Replace **`RESOURCE_GROUP`** with the desired name for your resource group, **`LOCATION`** with the Azure region where the resource group will be created, and **`CONFIG_FILE`** with the path to the configuration file.

The process of creating the resource group and deploying the configuration file may take several minutes. Once the deployment is complete, you can view the cluster in the Azure portal by clicking on the "Kubernetes services" item in the "All resources" list.
