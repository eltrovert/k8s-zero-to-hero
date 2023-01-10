# Setup Kubernetes Cluster On GCP Using GKE (Google Kubernetes Engine)

We will go over the steps for setting up a Kubernetes cluster on Google Cloud Platform (GCP) using the console, shell, or deployment manager.

## **Prerequisites**

Before setting up a Kubernetes cluster on GCP, you will need to have a GCP account and have the **`gcloud`** command-line tool installed on your local machine. You can sign up for a GCP account and install the **`gcloud`** tool by following the instructions on the GCP website: **[https://cloud.google.com/gcp/](https://cloud.google.com/gcp/)**.

## **Setting up a Kubernetes cluster using the console**

The easiest way to set up a Kubernetes cluster on GCP is to use the GCP console.

1. Log in to the GCP console (**[https://console.cloud.google.com/](https://console.cloud.google.com/)**).
2. Click on the "Navigation menu" (the three horizontal lines in the top-left corner of the screen) and select "Kubernetes Engine".
3. Click on the "Create cluster" button.
4. On the "Create a cluster" page, choose the desired settings for your cluster (e.g. number of nodes, machine type, region, etc.).
5. Click on the "Create" button to create the cluster.

The process of creating the cluster may take several minutes. Once the cluster is created, you can view it in the GCP console by clicking on the "Clusters" tab in the Kubernetes Engine page.

## **Setting up a Kubernetes cluster using the shell**

You can also set up a Kubernetes cluster on GCP using the **`gcloud`** command-line tool.

To create a Kubernetes cluster using the shell, run the following command:

```bash
gcloud container clusters create CLUSTER_NAME
```

Replace **`CLUSTER_NAME`** with the desired name for your cluster.

You can also specify additional options for the cluster, such as the number of nodes, machine type, and region, by using the **`--num-nodes`**, **`--machine-type`**, and **`--region`** flags, respectively. For example:

```bash
gcloud container clusters create CLUSTER_NAME --num-nodes=3 --machine-type=n1-standard-2 --region=us-central1
```

## **Setting up a Kubernetes cluster using Deployment Manager**

Deployment Manager is a GCP tool that allows you to define and deploy cloud resources using configuration files. You can use Deployment Manager to set up a Kubernetes cluster on GCP.

To set up a Kubernetes cluster using Deployment Manager on GCP, follow these steps:

1. Create a configuration file for your cluster. The configuration file should be written in YAML and should include the desired settings for your cluster (e.g. number of nodes, machine type, region, etc.).

Here is an example configuration file that creates a three-node Kubernetes cluster with **`n1-standard-2`** machine type in the **`us-central1`** region:

```yaml
resources:
- name: cluster
  type: container.v1.cluster
  properties:
    zone: us-central1-a
    cluster:
      name: CLUSTER_NAME
      initialNodeCount: 3
      nodeConfig:
        machineType: n1-standard-2
```

1. Save the configuration file to your local machine.
2. Use the **`gcloud`** command-line tool to create a Deployment Manager deployment using the configuration file. Run the following command:

```bash
gcloud deployment-manager deployments create DEPLOYMENT_NAME --config=CONFIG_FILE
```

Replace **`DEPLOYMENT_NAME`** with the desired name for your deployment and **`CONFIG_FILE`** with the path to the configuration file.

The process of creating the deployment may take several minutes. Once the deployment is created, you can view it in the GCP console by clicking on the "Deployment Manager" menu item in the Navigation menu.
