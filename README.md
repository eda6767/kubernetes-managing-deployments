# Kubernetes

<sub/>
Kubernetes, often abbreviated as K8s, is an open-source container orchestration platform designed to automate the deployment, scaling, and management of containerized applications. Originally developed by Google and later donated to the Cloud Native Computing Foundation (CNCF), Kubernetes provides a robust framework for container orchestration, making it easier to deploy and manage applications at scale. </sub>

<br/>
</br>

<sub/>
Key features of Kubernetes include: </sub>

<br/>
</br>


<sub/> <sub/> <sub/> 

* **Containerization:** It leverages container technology, such as Docker, to encapsulate applications and their dependencies, ensuring consistent deployment across various </sub> environments.  </sub>   </sub> </sub>






* **Cluster Management:** Kubernetes organizes containers into clusters, providing mechanisms for load balancing, service discovery, and high availability. 



* **Declarative Configuration:** Users define the desired state of their applications and infrastructure using configuration files, and Kubernetes ensures that the current state matches the declared state. 


* **Horizontal Scaling:** It enables automatic scaling of applications based on demand by dynamically adjusting the number of running containers. 


* **Self-healing:** Kubernetes monitors the health of containers and services. If a container or node fails, it automatically reschedules and replaces them to maintain the desired state. 


* **Service Discovery and Load Balancing:** Kubernetes offers built-in mechanisms for service discovery and load balancing, allowing applications to easily communicate with each other.  


* **Resource Management:** It allocates resources efficiently by allowing users to specify resource requirements and limits for containers. 



<sub/>
Kubernetes has become a cornerstone of cloud-native development and is widely adopted in modern software development environments, providing a scalable and flexible solution for managing containerized applications across diverse infrastructures.  </sub>


<br/>
</br>

<sub/>
This repository provides practice in scaling and managing containers delivering common scenarios where multiple heterogeneous deployments are being used. </sub>

<br/>
</br>


<sub/>

```
gcloud container clusters create myfirstcluster \
  --machine-type e2-small \
  --num-nodes 3 \
  --scopes "https://www.googleapis.com/auth/projecthosting,storage-rw"
```
</sub>

<br/>
</br>

<sub/>

```
kubectl explain deployment
```
</sub>



<sub/>

```
kubectl explain deployment --recursive
```
</sub>



<sub/>

```
kubectl explain deployment.metadata.name
```
</sub>


<sub/> Create a deployment </sub>



<sub/>

```
vi deployments/auth.yaml
```
</sub>


<sub/> We can change the image in the containers section of the deployment to the following: </sub>

<sub/>

```
...
containers:
- name: auth
  image: "kelseyhightower/auth:1.0.0"
...
```
</sub>

<sub/>  To save auth.yaml file press ESC and then :wq. To check whole yaml file type :  </sub>

<sub/>

```
cat deployments/auth.yaml
```
</sub>


<sub/>  Here we are creating one replica of the container.   </sub>


<sub/>

```
kubectl create -f deployments/auth.yaml
```
</sub>


<sub/>  Once we have created the deployment, we can verify that it was created:   </sub>

<sub/>

```
kubectl get deployments
```
</sub>






