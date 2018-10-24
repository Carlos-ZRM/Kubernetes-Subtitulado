

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
	- AppsCode.com proporciona clusters de Kubernetes administrados para varias nubes públicas, incluidas AWS y Google Cloud Platform.

APPUiO ejecuta una plataforma de nube pública OpenShift, que admite cualquier carga de trabajo de Kubernetes. Además, APPUiO ofrece Private Managed OpenShift Clusters, que se ejecutan en cualquier nube pública o privada.

Amazon Elastic Container Service para Kubernetes ofrece el servicio de Kubernetes administrado.

El servicio de Azure Kubernetes ofrece clusters de Kubernetes administrados.

Giant Swarm ofrece clusters de Kubernetes administrados en su propio centro de datos, en las instalaciones o en nubes públicas.

Google Kubernetes Engine ofrece clusters de Kubernetes administrados.

IBM Cloud Kubernetes Service ofrece clusters de Kubernetes administrados con opciones de aislamiento, herramientas operativas, información de seguridad integrada en imágenes y contenedores, e integración con Watson, IoT y datos.

Kubermatic proporciona clusters de Kubernetes administrados para varias nubes públicas, incluyendo AWS y Digital Ocean, así como en las instalaciones con la integración de OpenStack.

Kublr ofrece clusters de Kubernetes seguros, escalables y seguros de nivel empresarial en AWS, Azure, GCP y en las instalaciones. Incluye copia de seguridad y recuperación de desastres listas para usar, registro y monitoreo centralizado de múltiples clústeres y alertas incorporadas.

Madcore.Ai es una herramienta CLI centrada en devops para implementar la infraestructura de Kubernetes en AWS. Maestro, nodos de grupo de escalado automático con instancias puntuales, ingress-ssl-lego, Heapster y Grafana.

OpenShift Dedicated ofrece clusters de Kubernetes administrados impulsados ​​por OpenShift.

OpenShift Online proporciona acceso alojado gratuito para aplicaciones Kubernetes.

Oracle Container Engine para Kubernetes es un servicio totalmente gestionable, escalable y de alta disponibilidad que puede utilizar para implementar sus aplicaciones en contenedores en la nube.

Platform9 ofrece Kubernetes administrados en las instalaciones o en cualquier nube pública, y proporciona monitoreo y alerta de salud 24/7. (Kube2go, un servicio de implementación de clúster Kubernetes de Plataforma UI impulsado por la plataforma web9 lanzado, se ha integrado a Platform9 Sandbox)

Stackpoint.io proporciona la gestión y automatización de la infraestructura de Kubernetes para múltiples nubes públicas
- Servicios en la nube
- Soluciones On-Premises

https://kubernetes.io/docs/setup/pick-right-solution/#table-of-solutions

https://kubernetes.io/docs/setup/

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI2NDYyMjA0MiwtMTU1MDk3OTgyMiw3Mz
A5OTgxMTZdfQ==
-->