# Setup kubectl context to Connect to Kubernetes Cluster

In order to use kubectl to communicate with a cluster, you need to set the correct context. The context specifies the cluster and the user account that kubectl will use to access the cluster.

In this article, we will go over how to get the kubectl context for a cluster created using Minikube, Microk8s, Google Kubernetes Engine (GKE), Amazon Elastic Container Service for Kubernetes (EKS), and Azure Kubernetes Service (AKS).

## **Getting the kubectl context for a Minikube cluster**

To get the kubectl context for a Minikube cluster, run the following command:

```bash
kubectl config use-context minikube
```

This will set the context to the Minikube cluster running on your local machine.

## **Getting the kubectl context for a Microk8s cluster**

To get the kubectl context for a Microk8s cluster, run the following command:

```bash
microk8s kubectl config use-context microk8s
```

This will set the context to the Microk8s cluster running on your local machine.

## **Getting the kubectl context for a GKE cluster**

To get the kubectl context for a Google Kubernetes Engine (GKE) cluster, you will need to authenticate the **`gcloud`** command-line tool using your Google Cloud account, set the current project to the project containing your GKE cluster, and set the current compute zone to the zone where your GKE cluster is located.

1. Authenticate the **`gcloud`** command-line tool using your Google Cloud account. Run the following command:
    
    ```
    gcloud auth login
    ```
    
2. Set the current project to the project containing your GKE cluster. Run the following command:
    
    ```
    gcloud config set project PROJECT_ID
    ```
    
    Replace **`PROJECT_ID`** with the ID of your project.
    
3. Set the current compute zone to the zone where your GKE cluster is located. Run the following command:
    
    ```
    gcloud config set compute/zone ZONE
    ```
    
    Replace **`ZONE`** with the name of the zone (e.g. **`us-central1-a`**).
    
4. Once the **`gcloud`** tool is authenticated and the current project and compute zone are set, run the following command to get the kubectl context for your GKE cluster:
    
    ```
    gcloud container clusters get-credentials CLUSTER_NAME
    ```
    
    Replace **`CLUSTER_NAME`** with the name of your GKE cluster.
    

This will update your kubectl configuration with the information needed to access your GKE cluster. You should now be able to use kubectl to communicate with your GKE cluster

## **Getting the kubectl context for an EKS cluster**

To get the kubectl context for an Amazon Elastic Container Service for Kubernetes (EKS) cluster, you will need to install the **`aws-iam-authenticator`** tool and configure your AWS CLI credentials.

1. Install the **`aws-iam-authenticator`** tool. You can find instructions for installing the **`aws-iam-authenticator`** tool on the AWS website: **[https://docs.aws.amazon.com/eks/latest/userguide/install-aws-iam-authenticator.html](https://docs.aws.amazon.com/eks/latest/userguide/install-aws-iam-authenticator.html)**
2. Configure your AWS CLI credentials. You can find instructions for configuring the AWS CLI on the AWS website: **[https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)**
3. Once the **`aws-iam-authenticator`** tool is installed and the AWS CLI is configured, run the following command to get the kubectl context for your EKS cluster:
    
    ```bash
    aws eks update-kubeconfig --name CLUSTER_NAME
    ```
    
    Replace **`CLUSTER_NAME`** with the name of your EKS cluster.
    

This will update your kubectl configuration with the information needed to access your EKS cluster. You should now be able to use kubectl to communicate with your EKS cluster.

I hope these instructions were helpful in getting the kubectl context for an EKS cluster. If you have any questions or need further assistance, please

## **Getting the kubectl context for an AKS cluster**

To get the kubectl context for an Azure Kubernetes Service (AKS) cluster, you will need to install the **`az`** command-line tool and log in to your Azure account.

1. Install the **`az`** command-line tool. You can find instructions for installing the **`az`** tool on the Azure website: **[https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)**
2. Log in to your Azure account. You can log in to your Azure account by running the following command:
    
    ```bash
    az login
    ```
    
3. Once the **`az`** tool is installed and you are logged in, run the following command to get the kubectl context for your AKS cluster:
    
    ```bash
    az aks get-credentials --resource-group RESOURCE_GROUP --name CLUSTER_NAME
    ```
    
    Replace **`RESOURCE_GROUP`** with the name of the resource group containing your AKS cluster and **`CLUSTER_NAME`** with the name of your AKS cluster.
    

This will update your kubectl configuration with the information needed to access your AKS cluster. You should now be able to use kubectl to communicate with your AKS cluster.

I hope these instructions were helpful in getting the kubectl context for an AKS cluster. If you have any questions or need further assistance, please don't hesitate to ask.