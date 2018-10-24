

Existen varias formas para crear un cluster de Kubernetes. La instalación se decidira a partir de la infraestructura disponible (PC, VM, IaaS ... ), del tamaño del cluster (Laboratorio de pruebas, cluster para un microservicio o incluso implementar una PaaS). También se pueden elegir distribuciones de Kubernetes que cuantan con servicios y configuraciones modificadas o ya creadas. (OpenShift, IBM Cloud Kubernetes Service) 
- Instalación en maquinas locales o barematal
	-   Minikube
			Es un método para crear un clúster local de Kubernetes de un solo nodo para el desarrollo y las pruebas. La configuración está completamente automatizada y no requiere una cuenta de proveedor en la nube.
	-	IBM Cloud Private-CE (Community Edition 
	Se utilizan maquinas virtuales en la maquina virtual parael despliegue de Kubernetes para escenarios de prueba, se pueden escalar a un cluster multinodos.
	-	Kubeadm-dind
	Es un clúster de kubernetes de varios nodos que solo requiere un demonio docker. Utiliza la técnica docker-in-docker para generar el clúster Kubernetes
- Servicios alojados
	Proporcionan luster de kubernetes administrados
	
	-	Amazon Elastic Container Service for Kubernetes 
	-  Azure Kubernetes Service
	-  Google Kubernetes Engine
	- IBM Cloud Kubernetes Service
Kubermatic provides managed Kubernetes clusters for various public clouds, including AWS and Digital Ocean, as well as on-premises with OpenStack integration.

Kublr offers enterprise-grade secure, scalable, highly reliable Kubernetes clusters on AWS, Azure, GCP, and on-premise. It includes out-of-the-box backup and disaster recovery, multi-cluster centralized logging and monitoring, and built-in alerting.

Madcore.Ai is devops-focused CLI tool for deploying Kubernetes infrastructure in AWS. Master, auto-scaling group nodes with spot-instances, ingress-ssl-lego, Heapster, and Grafana.

OpenShift Dedicated offers managed Kubernetes clusters powered by OpenShift.

OpenShift Online provides free hosted access for Kubernetes applications.

Oracle Container Engine for Kubernetes is a fully-managed, scalable, and highly available service that you can use to deploy your containerized applications to the cloud.

Platform9 offers managed Kubernetes on-premises or on any public cloud, and provides 24/7 health monitoring and alerting. (Kube2go, a web-UI driven Kubernetes cluster deployment service Platform9 released, has been integrated to Platform9 Sandbox.)

Stackpoint.io provides Kubernetes infrastructure automation and management for multiple public clouds
- Servicios en la nube
- Soluciones On-Premises

https://kubernetes.io/docs/setup/pick-right-solution/#table-of-solutions

https://kubernetes.io/docs/setup/

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY2Mzg0MTM0NiwtMTU1MDk3OTgyMiw3Mz
A5OTgxMTZdfQ==
-->