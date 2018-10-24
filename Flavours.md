

Existen varias formas para crear un cluster de Kubernetes. La instalación se decidira a partir de la infraestructura disponible (PC, VM, IaaS ... ), del tamaño del cluster (Laboratorio de pruebas, cluster para un microservicio o incluso implementar una PaaS). También se pueden elegir distribuciones de Kubernetes que cuantan con servicios y configuraciones modificadas o ya creadas. (OpenShift, IBM Cloud Kubernetes Service) 
- Instalación en maquinas locales o barematal
	-   Minikube
			Es un método para crear un clúster local de Kubernetes de un solo nodo para el desarrollo y las pruebas. La configuración está completamente automatizada y no requiere una cuenta de proveedor en la nube.
	-	IBM Cloud Private-CE (Community Edition 
	Se utilizan maquinas virtuales en la maquina virtual parael despliegue de Kubernetes para escenarios de prueba, se pueden escalar a un cluster multinodos.
	-	Kubeadm-dind
	Es un clúster de kubernetes de varios nodos que solo requiere un demonio docker. Utiliza la técnica docker-in-docker para generar el clúster Kubernetes
- Servicios alojados
	Proporcionan clúster de kubernetes administrados
	
	-	Amazon Elastic Container Service for Kubernetes 
	-  Azure Kubernetes Service
	-  Google Kubernetes Engine
	- IBM Cloud Kubernetes Service
	- OpenShift Dedicated offers managed Kubernetes clusters
	- OpenShift Online
	- Oracle Container Engine for Kubernetes automation and management for multiple public clouds
- Servicios en la nube
	Estas soluciones le permiten crear clústeres Kubernetes en una variedad de proveedores de IaaS.
	- Alibaba Cloud
	 - AWS
	 - Azure
	 - Google Compute Engine (GCE)
	 - IBM Cloud
	 - Oracle Container Engine for K8s
	 - Rancher 2.0 
- Soluciones On-Premises
	Estas soluciones le permiten crear clústeres Kubernetes en su red interna, segura y en la nube
	- GKE On-Prem
	- Rancher 2.0
	- SUSE CaaS Plataform
	- SUSE Cloud Application Platform

https://kubernetes.io/docs/setup/pick-right-solution/#table-of-solutions

https://kubernetes.io/docs/setup/

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEzMTgzMDU2NCwtMTc5OTI3ODYwOCwtMT
U1MDk3OTgyMiw3MzA5OTgxMTZdfQ==
-->