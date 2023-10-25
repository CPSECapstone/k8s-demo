![](https://logos-world.net/wp-content/uploads/2023/06/Kubernetes-Logo.png)

# Kubernetes (k8s)
#### **Prerequisites**
- Familiarity with container technologies such as Docker

### **Overview**
- **Why Kubernetes?**
- **Design principles**
- **Basic objects in Kuberentes**
- **The kuberentes control plane**
- **When not to use Kubernetes**
- **Live Demo**
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
    
    The most important design principle in Kubernetes is that we simply define the desired state of our system and let Kubernetes automation work to ensure that the actual state of the system reflects these desires.

- Distributed
    
    Kubernetes is designed to provide the infrastructural layer for distributed systems, yielding clean abstractions to build applications on top of a collection of machines (collectively known as a cluster).

    ![](https://www.jeremyjordan.me/content/images/2019/11/distributed_systems.png)

- Decoupled
    
    It is commonly recommended that containers be developed with a single concern in mind. As a result, developing containerized applications lends itself quite nicely to the microservice architecture design pattern, which recommends "designing software applications as suites of independently deployable services."
    
- Immutable infrastructure
    
    In order to achieve the most benefit from containers and container orchestration, you should be deploying immutable infrastructure. This is, rather than logging in to a container on a machine to make changes (eg. updating a library), you should build a new container image, deploy the new version, and terminate the older version.

### **Basic objects in Kubernetes**
- Pod

    The Pod object is the fundamental building block in Kubernetes, comprised of one or more (tightly related) containers, a shared networking layer, and shared filesystem volumes.
    
    ![](https://www.jeremyjordan.me/content/images/2019/11/pod.png)

- Deployment

    A Deployment object encompasses a collection of pods defined by a template and a replica count (how many copies of the template we want to run). You can either set a specific value for the replica count or use a separate Kubernetes resource (eg. a horizontal pod autoscaler) to control the replica count based on system metrics such as CPU utilization.

    ![](https://www.jeremyjordan.me/content/images/2019/11/deployment.png)

- Service (SVC)

    Each Pod in Kubernetes is assigned a unique IP address that we can use to communicate with it. However, because Pods are ephemeral, it can be quite difficult to send traffic to your desired container.

    ![](https://www.jeremyjordan.me/content/images/2019/11/service-1.png)

- Ingress

    While a Service allows us to expose applications behind a stable endpoint, the endpoint is only available to internal cluster traffic. If we wanted to expose our application to traffic external to our cluster, we need to define an Ingress object.  

    ![](https://www.jeremyjordan.me/content/images/2019/11/ingress_2.png)

- Job

    The Kubernetes objects I've described up until this point can be composed to create reliable, long-running services. In contrast, the Job object is useful when you want to perform a discrete task.

- ...and many more
    - StatefulSet (STS): Similar to a Deployment, but for when you need to run a stateful application.
    - Volume: For managing directories mounted onto Pods.
    - Secret: For storing sensitive credentials.
    - Namespace (NS): For separating resources on your cluster.

### **The kubernetes control plane**
By this point, you're probably wondering how Kubernetes is capable of taking all of our object specifications and actually executing these workloads on a cluster.
- Master node
- Worker node

![](https://www.jeremyjordan.me/content/images/2019/11/full_picture-1.png)

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