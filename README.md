# Kubernetes-Subtitulado
Este git es un tutorial de la instalación de Kubernetes. Tiene como proposito no solo el despliegue de un cluster sino también uan revisión de los conceptos de CloudComputing

## ¿Qué es Kubernetes?

Kubernetes es un sistema open-source (PaaS) para despliegues automáticos, escalamiento y administración de aplicaciones contenerizadas

## Características de Kubernetes

Creación de servicios y balanceo de carga

- No es necesario modificar su aplicación para utilizar un mecanismo de creación de servicio desconocido. Kubernetes les da a los contenedores sus propias direcciones IP y un solo nombre DNS para un conjunto de contenedores, y pueden equilibrar la carga entre ellos. 

Empaquetado automático

Coloca automáticamente los contenedores según sus requisitos de recursos y otras restricciones, sin sacrificar la disponibilidad. Combine cargas de trabajo críticas y de mejor esfuerzo para aumentar la utilización y ahorrar aún más recursos.
Orquestación de almacenamiento

Monte automáticamente el sistema de almacenamiento de su elección, ya sea de almacenamiento local, un proveedor de nube pública como GCP o AWS, o un sistema de almacenamiento en red como NFS, iSCSI, Gluster, Ceph, Cinder o Flocker.
Autocuración

Reinicia los contenedores que fallan, reemplaza y reprograma los contenedores cuando los nodos mueren, elimina los contenedores que no responden a su control de salud definido por el usuario y no los anuncia a los clientes hasta que estén listos para servir.
Despliegues automatizados y rollbacks

Kubernetes implementa progresivamente los cambios en su aplicación o su configuración, mientras supervisa el estado de la aplicación para asegurarse de que no destruya todas sus instancias al mismo tiempo. Si algo sale mal, Kubernetes revertirá el cambio por ti. Aproveche un creciente ecosistema de soluciones de despliegue.
Secreto y gestión de la configuración.

Implemente y actualice los secretos y la configuración de la aplicación sin reconstruir su imagen y sin exponer secretos en la configuración de su pila.
Ejecución por lotes

Además de los servicios, Kubernetes puede administrar sus cargas de trabajo por lotes y CI, reemplazando los contenedores que fallan, si lo desea.
Escala horizontal

Escale su aplicación hacia arriba y hacia abajo con un comando simple, con una interfaz de usuario o automáticamente en función del uso de la CPU.  
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxNzI0Mzc3OF19
-->