# Kubernetes-Subtitulado
Este git es un tutorial de la instalación de Kubernetes. Tiene como proposito no solo el despliegue de un cluster sino también uan revisión de los conceptos de CloudComputing

## ¿Qué es Kubernetes?

Kubernetes es un sistema open-source (PaaS) para despliegues automáticos, escalamiento y administración de aplicaciones contenerizadas.
Kubernetes proporciona un entorno de gestión centrado en contenedores. Orquesta la infraestructura de computación, redes y almacenamiento

## Características de Kubernetes

- Creación de servicios y balanceo de carga

	:	No es necesario modificar su aplicación para utilizar un mecanismo de creación de servicio desconocido. Kubernetes les da a los contenedores sus propias direcciones IP y un solo nombre DNS para un conjunto de contenedores, y pueden equilibrar la carga entre ellos. Puedes crear micro-servicios y crear replicas de este, Kubernetes hará un balanceo de carga entre las replicas y solo se necesitara un nombre DNS para acceder al servicio.

- Empaquetado automático

	:	Kubernetes coloca automáticamente los contenedores en los servidores según sus requisitos de recursos y otras restricciones, sin sacrificar la disponibilidad. Combina cargas de trabajo críticas y de mejor esfuerzo para aumentar la utilización y ahorrar aún más recursos.

- Orquestación de almacenamiento

	:	Monte automáticamente el sistema de almacenamiento de su elección, ya sea de almacenamiento local, un proveedor de nube pública como GCP o AWS, o un sistema de almacenamiento en red como NFS, iSCSI, Gluster, Ceph, Cinder o Flocker. 

- Autoreparación

	:	Kubernete reinicia los contenedores que fallan, reemplaza y reprograma los contenedores cuando los nodos mueren, elimina los contenedores que no responden a su control de salud definido por el usuario y no los anuncia a los clientes hasta que estén listos para servir.

- Despliegues automatizados y rollbacks

	:	Kubernetes implementa progresivamente los cambios en su aplicación o su configuración, mientras supervisa el estado de la aplicación para asegurarse de que no destruya todas sus instancias al mismo tiempo. Si algo sale mal, Kubernetes revertirá el cambio por ti. Aproveche un creciente ecosistema de soluciones de despliegue.

- Secretos y gestión de la configuración.

	:	Implemente y actualice los secretos [^1] y la configuración de la aplicación sin reconstruir su imagen y sin exponer secretos en la configuración de su pila.


- Ejecución por lotes

	:	Además de los servicios, Kubernetes puede administrar sus cargas de trabajo por lotes y CI, reemplazando los contenedores que fallan, si lo desea.

- Escala horizontal

		: scale su aplicación hacia arriba y hacia abajo con un comando simple, con una interfaz de usuario o automáticamente en función del uso de la CPU.  

## Conceptos básicos de Kubernetes


[^1]:	 Un Secreto es un objeto que contiene una pequeña cantidad de datos confidenciales, como una contraseña, un token o una clave. Dicha información se podría incluir en la especificación del Pod o en una imagen; ponerlo en un objeto Secreto permite un mayor control sobre cómo se usa, y reduce el riesgo de exposición accidental.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQwODY2OTA2MCwtODAzMzMzNDQ4LDIyOT
U3NDM2NSwtMjc5NTE2MDU1LDg0Njk4ODIzNCwxMDEzNTA0Mzky
XX0=
-->