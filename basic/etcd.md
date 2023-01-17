# Enter ETCD: The Database Room

**Kube-API-Server:** Ahh we meet again! Where are you going?

**You:** We are going to ETCD room. Would you like to follow us?

**Kube-API-Server:** Ah, the ETCD room, one of my favorite places in the Kubernetes party! As the kube-api-server, I'm the one who's responsible for receiving and handling API requests, and the ETCD room is where I go to get all the important information that I need to do my job.

**Scheduler:** I guess it’s better for Kube-API-Server to showing you around ETCD room, he’s and expert in it. 

**You:** I wouldn’t mind. See you around Scheduler!

---

**Kube-API-Server**

The ETCD room is where all the configuration data of the Kubernetes party is stored, it's like the file room of the party where all the important information of the party is stored. It's a distributed key-value store that holds the entire state of the party, and all components rely on it to function properly.

When you enter the ETCD room, you'll notice that it's well-organized and easy to navigate. You'll see rows and rows of shelves, each one filled with important information about the party. The shelves are labeled with different categories such as pods, services, and deployments, so you can easily find the information you need.

It's always busy in the ETCD room, with different components coming in and out to retrieve and update information. But don't worry, the ETCD room is also staffed with experts who are happy to help you find what you need.

Just like a file room in a party, it's important to handle the ETCD room with care and follow best practices when working with it. But don't hesitate to ask for help if you need it, the experts are always there to help you.

**You:** Can you elaborate more on the data being stored at ETCD?

**Kube-API-Server:** I can tell you that the ETCD room stores a wide variety of data that is critical to the functioning of the Kubernetes party.

The most important data that is stored in the ETCD room is the configuration data of the party. This includes information such as:

- the state of all the objects in the party such as pods, services, and deployments
- the desired state of the party and the current state of the party
- the configuration of all the different components such as the kube-api-server, the kube-controller-manager, and the kube-scheduler.

It's like a file room where all the important information of the party is stored, it's important for the party to run smoothly and for other components to do their jobs.

Additionally, the ETCD room also stores data related to authentication and authorization, such as the credentials used by different components to access the API and the rules that govern which users and components are allowed to perform specific actions.

**You:** Does etcd also save manifest of resources that are deployed to Kubernetes?

**Kube-API-Server:** I can confirm that the ETCD room also stores the manifest of resources that are deployed to Kubernetes. The manifest files are written in YAML or JSON format and they describe the desired state of the party, including details of all the guests (pods) that are expected to be running, the services that need to be exposed, and the configurations of the different components.

When you create, update, or delete any resource in the party, kube-api-server sends the request to the ETCD room and the etcd stores the data of the request and also updates the state of the party accordingly.

For example, when you deploy a new guest (pod) to the party, the manifest file describes the details of the guest, such as the image to be used, the resources required, and the command to be executed. The kube-api-server sends the request to the ETCD room to create the guest and the ETCD room stores the manifest of the guest, and updates the state of the party accordingly.

**You:** Between You, etcd, scheduler, or controller-manager. Which one has more important role in Kubernetes?

**Kube-API-server:** I would say that all the components in Kubernetes play an important role and work together to ensure that the party runs smoothly. Each component has its unique responsibilities and they all work together to ensure the party runs seamlessly.

For example, as the kube-api-server, I am responsible for receiving and handling API requests, and I rely on the ETCD room to get the necessary information to do my job. The ETCD room, in turn, relies on the kube-controller-manager and kube-scheduler to ensure that the party is running according to the desired state. And the kube-scheduler relies on the kubelet to ensure that the guests (pods) are running on the right partygoers (nodes).

It's like a well-oiled machine, every component has its own role and responsibilities but they all work together to make sure the party runs smoothly. The importance of each component depends on the use case and the specific requirements of the party.

**You:** Is there anyone aside from You, etcd, scheduler, and controller-manager that I need to meet at Kubernetes control-plane room?

**Kube-API-server:** There are other important external components in the control-plane room aside from the kube-api-server, kube-controller-manager, kube-scheduler, and ETCD, such as kubeadm, kubectl, and kubeconfig. Each of them plays an important role in the party and you may want to meet them to understand more about the party and how to navigate it.