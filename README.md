# Kubernetes (k8s)
![](https://logos-world.net/wp-content/uploads/2023/06/Kubernetes-Logo.png)
#### **Prerequisites**
- Familiarity with container technologies such as Docker

### **Overview**
Here's what we'll discuss today. Click on any top-level heading to jump directly to that section.
- [**Why Kubernetes?**]()
- [**Design principles**]()
- [**Basic objects in Kuberentes**]()
- [**The kuberenetes control plane**]()
- [**When not to use Kubernetes**]()
- [**Live Demo**]()
- **Q&A**

### **Why Kuberenetes?**
- Kubernetes is often described as a container orchestration platform
- Why de we use containers?
    - Containers provide a lightweight mechanism for isolating an application's environment.
- What's missing in containers?
    - What happens if your container dies?
    - What happens if the machine running your container fails?
    - Containers do not provide a solution for fault tolerance.
- Using a container orchestration platform like Kubernetes we can address many of these concerns mentioned. 
- A container orchestration platform manages the entire lifecycle of individual containers, spinning up and shutting down resources as needed.

### **Design principles**
Now that we understand the motivation for container orchestration in general, let's spend some time to discuss the motivating design principles behind Kubernetes.
- Declarative
- Distributed
- Decoupled
- Immutable infrastructure

### **Basic objects in Kubernetes**
- Pod
- Deployment
- Service (SVC)
- Ingress
- Job
- ...and many more
    - StatefulSet (STS)
    - Volume
    - Secret 
    - Namespace (NS)


### **The kuberenetes control plane**
- Master node
- Worker node


### **When not to use Kubernetes**
- You can run your workload on a single machine.
- Your compute needs are light.
- You don't need high availability and can tolerate downtime.
- You don't envision making a lot of changes to your deployed services.
- You have a monolithic architecture and don't plan to separate it into microservices.

### **Live Demo**
Technologies:
1. Homebrew 
2. Docker
3. Minikube
4. Kubectl
5. Helm

### **Q&A**