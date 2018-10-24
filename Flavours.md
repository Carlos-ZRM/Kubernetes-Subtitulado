

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
	- OpenShift Dedicated offers managed Kubernetes clusters
	- OpenShift Online
	- Oracle Container Engine for Kubernetes automation and management for multiple public clouds
- Servicios en la nube
- Soluciones On-Premises

https://kubernetes.io/docs/setup/pick-right-solution/#table-of-solutions

https://kubernetes.io/docs/setup/

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYwMzg0NTg1MiwtMTU1MDk3OTgyMiw3Mz
A5OTgxMTZdfQ==
-->