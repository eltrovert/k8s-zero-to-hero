# Meet kubelet: The Party’s Helper

<aside>
🃏 We have explore almost every part of the control-plane room, now let’s meet with the one responsible of managing the Worker Node
I’m a magician, a mentalist. I can read your mind!
Half of your mind are saying that you already know what iKubelet is, you’ve read it everywhere and do not need my explaination. But half of it carving to know what does Kubelet does in more detail. So let’s understand Kubelet in more details!
</aside>

# What is Kubelet?

Ah, the question of the hour! Kubernetes kubelet is an essential component of the Kubernetes orchestration platform. It's essentially the "worker node" of the system, responsible for running pods (groups of one or more containers) on a particular node. Think of it like the foreman on a construction site - it's the one in charge of making sure all the little worker bees (the containers) are doing their jobs correctly. It's a pretty important piece of the puzzle, and without it, the whole system would grind to a halt.

But let me give you an analogy that might make it easier to understand. Imagine you're hosting a dinner party at your house. You've got a bunch of dishes to prepare, and you want to make sure everything is cooked to perfection. So you divide up the tasks among your guests - one person is in charge of the roast, another is making the salad, and so on. But you don't want to have to keep track of all of them individually, so you assign one person to be the "head chef." That person is in charge of making sure everything is running smoothly, that the dishes are coming out on time, and that the roast isn't burnt to a crisp. That's the kubelet's job in the Kubernetes system - it's the one making sure all the containers are running properly.

# What it does behind the veil?

In a bit more detail, the kubelet is responsible for several key tasks within the Kubernetes system. First and foremost, it's responsible for starting, stopping, and maintaining the containers that make up a pod. It communicates with the API server (the "brain" of the system) to receive instructions on which pods should be running, and then it makes sure that they are indeed running. If a container crashes or needs to be updated, the kubelet takes care of it.

Additionally, the kubelet is responsible for reporting the status of the pods and nodes to the API server. This includes things like how much CPU and memory the pods are using, whether they're running or not, and if there are any errors. This information is used by other parts of the Kubernetes system to make decisions, such as whether to scale up or down the number of replicas of a particular pod.

It also acts as an intermediary between the container runtime and the kube-apiserver, it can interact with the container runtime to create/update/delete container and also it can interact with kube-apiserver for pod updates and pod status updates.

Another important role of the kubelet is container image management. It's responsible for pulling down the container images for pods when they're created, and for ensuring that the correct versions of the images are running. This includes checking for updates and pulling down new versions when they're available.

Well, there's one more thing I'd like to add that might be of interest to you. The kubelet is also responsible for handling "node-level" events, such as when a disk is running out of space, or when a node is rebooted. It can take actions to remediate these events, such as rescheduling pods to different nodes, or deleting old log files to free up space.

Another cool feature of kubelet is that it also supports optional plugins that can be used to customize the behavior of kubelet in certain scenarios. For example, you can use a plugin to automatically provision storage for new pods, or to automatically configure networking for a pod.

And one more thing to mention is the kubelet can also run in standalone mode, it can run without connecting to the API server. This is useful in scenarios where you have a single node cluster or where the API server is not available.

As you can see, the kubelet is a versatile and powerful component of the Kubernetes system, it's responsible for a wide variety of tasks that keep the system running smoothly. It's a pretty essential piece of the puzzle, and it's definitely something worth understanding if you're working with Kubernetes.

# Let’s Summarize!

In summary, the kubelet is the worker node of the Kubernetes system, it makes sure that the pods are running correctly and it reports the status of the pods and nodes to the API server. It's a crucial part of the Kubernetes orchestration platform, and without it, the whole system would fall apart.