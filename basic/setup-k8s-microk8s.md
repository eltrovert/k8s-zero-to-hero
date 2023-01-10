# Setup Kubernetes Cluster On Local Machine using Microk8s

Microk8s is a lightweight, fast, and reliable Kubernetes distribution that can be easily installed on a variety of platforms, including Linux, macOS, and Windows. It is a good choice for developers who want a quick and easy way to get started with Kubernetes, and it has many of the same features as Minikube, including support for deploying and managing applications, as well as debugging and troubleshooting.

In this article, we will walk through the steps to set up a Microk8s cluster on three of the most popular operating systems: Linux, macOS, and Windows.

# **Setting up Microk8s on Linux**

To set up Microk8s on a Linux machine, you will need to have the following prerequisites installed:

- A package manager (such as apt or yum)

Once you have these prerequisites installed, you can follow these steps to set up Microk8s:

1. Download and install Microk8s by running the following command:

```bash
sudo snap install microk8s --classic
```

1. Start the Microk8s cluster by running the following command:

```bash
microk8s start
```

1. Wait for the cluster to finish starting up. This may take a few minutes.
2. Once the cluster is up and running, you can check the status by running the following command:

```bash
microk8s status
```

# **Setting up Microk8s on macOS**

To set up Microk8s on a macOS machine, you will need to have the following prerequisites installed:

- Homebrew (package manager for macOS)

Once you have these prerequisites installed, you can follow these steps to set up Microk8s:

1. Download and install Microk8s by running the following command:

```bash
brew install microk8s
```

1. Start the Microk8s cluster by running the following command:

```bash
microk8s start
```

1. Wait for the cluster to finish starting up. This may take a few minutes.
2. Once the cluster is up and running, you can check the status by running the following command:

```bash
microk8s status
```

# **Setting up Microk8s on Windows**

To set up Microk8s on a Windows machine, you will need to have the following prerequisites installed:

- Chocolatey (package manager for Windows)

Once you have these prerequisites installed, you can follow these steps to set up Microk8s:

1. Download and install Microk8s by running the following command:

```bash
choco install microk8s
```

1. Start the Microk8s cluster by running the following command:

```bash
microk8s start
```

1. Wait for the cluster to finish starting up. This may take a few minutes.
2. Once the cluster is up and running, you can check the status by running the following command:

```bash
microk8s status
```

That's it! You should now have a working Microk8s cluster on your local machine, ready to deploy and test your applications.

Overall, Microk8s is a great tool for running a single-node Kubernetes cluster on your local machine, and it is easy to install and use on a variety of operating systems. If you're looking for a quick and easy way to get started with Kubernetes
