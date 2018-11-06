# Qué es un pod
Un pod (como en un pod de ballenas o guisantes) es un grupo de uno o más contenedores (como los contenedores Docker), con almacenamiento y red compartidos, y una especificación sobre cómo ejecutar los contenedores. Los contenidos de un pod siempre se colocan y se programan conjuntamente, y se ejecutan en un contexto compartido. Un pod modela un "host lógico" específico de la aplicación (contiene uno o más contenedores de aplicaciones que están relativamente estrechamente acoplados) en un mundo pre-contenedor, ejecutarse en la misma máquina virtual o física significaría ejecutarse en el mismo host lógico .  
  
Si bien Kubernetes admite más tipos de contenedor que solo Docker, Docker es el tipo más conocido, y ayuda a describir los pods en términos de Docker.  
  
El contexto compartido de un pod es un conjunto de espacios de nombres de Linux, cgroups y potencialmente otras facetas de aislamiento, las mismas cosas que aíslan un contenedor de Docker. En el contexto de un pod, las aplicaciones individuales pueden tener más sub-aislamientos aplicados.  
  
Los contenedores dentro de un pod comparten una dirección IP y espacio de puerto, y se pueden encontrar a través de localhost. También pueden comunicarse entre sí utilizando comunicaciones estándar entre procesos como los semáforos de SystemV o la memoria compartida POSIX. Los contenedores en diferentes pods tienen direcciones IP distintas y no pueden comunicarse por IPC sin una configuración especial. Estos contenedores generalmente se comunican entre sí a través de direcciones IP de Pod.  
  
Las aplicaciones dentro de un pod también tienen acceso a volúmenes compartidos, que se definen como parte de un pod y están disponibles para ser montados en el sistema de archivos de cada aplicación.  
  
En términos de construcciones de Docker, un pod se modela como un grupo de contenedores de Docker con espacios de nombres compartidos y volúmenes compartidos.  
  
Al igual que los contenedores de aplicaciones individuales, las cápsulas se consideran entidades relativamente efímeras (en lugar de duraderas). Como se discutió en la vida de un pod, los pods se crean, se les asigna una ID única (UID) y se programan en los nodos donde permanecen hasta la terminación (según la política de reinicio) o la eliminación. Si un nodo muere, los pods programados para ese nodo están programados para su eliminación, después de un período de tiempo de espera. Un pod dado (como lo define un UID) no se "reprograma" a un nuevo nodo; en su lugar, puede reemplazarse por un pod idéntico, incluso con el mismo nombre si lo desea, pero con un nuevo UID (consulte el controlador de replicación para obtener más detalles).  
  
Cuando se dice que algo tiene la misma vida útil que un pod, como un volumen, eso significa que existe mientras exista ese pod (con ese UID). Si ese pod se elimina por cualquier motivo, incluso si se crea un reemplazo idéntico, la cosa relacionada (por ejemplo, el volumen) también se destruye y se crea de nuevo.

## Administración

Los Pod son un modelo del patrón de múltiples procesos de cooperación que forman una unidad de servicio cohesiva. Simplifican la implementación y la administración de la aplicación al proporcionar una abstracción de mayor nivel que el conjunto de sus aplicaciones constitutivas. Los pods sirven como unidad de despliegue, escala horizontal y replicación. La asignación (co-programación), el destino compartido (por ejemplo, la terminación), la replicación coordinada, el uso compartido de recursos y la gestión de dependencias se manejan automáticamente para los contenedores en un pod.  
Intercambio de recursos y comunicación.  
  
Los pods permiten el intercambio de datos y la comunicación entre sus constituyentes.  
  
Todas las aplicaciones en un pod utilizan el mismo espacio de nombres de red (la misma IP y el mismo espacio de puerto) y, por lo tanto, pueden "encontrarse" entre sí y comunicarse utilizando localhost. Debido a esto, las aplicaciones en un pod deben coordinar su uso de puertos. Cada pod tiene una dirección IP en un espacio de red compartido plano que tiene comunicación completa con otras computadoras físicas y pods a través de la red.  
  
El nombre de host se establece en el Nombre del pod para los contenedores de aplicaciones dentro del pod. Más detalles sobre redes.  
  
Además de definir los contenedores de aplicaciones que se ejecutan en el pod, el pod especifica un conjunto de volúmenes de almacenamiento compartido. Los volúmenes permiten que los datos sobrevivan a reinicios de contenedores y se compartan entre las aplicaciones dentro del pod.

# Service

Las Pods en Kubernetes son mortales. Nacen y cuando mueren, no resucitan. Un ReplicaSets, en particular, crea y destruye Pods dinámicamente (por ejemplo, al escalar hacia arriba o hacia abajo). Si bien cada Pod tiene su propia dirección IP, no se puede confiar en que esas direcciones IP sean estables a lo largo del tiempo. Esto conduce a un problema: si algún conjunto de Pods (llamémoslos backends) proporciona funcionalidad a otros Pods (llamémoslos frontends) dentro del clúster de Kubernetes, ¿cómo se encuentran y descubren esos frontends qué backends hay en ese set?  
  
Entrar en Servicios.  
  
Un Servicio Kubernetes es una abstracción que define un conjunto lógico de Pods y una política mediante la cual acceder a ellos, a veces llamado un microservicio. El conjunto de Pods a los que apunta un Servicio está (generalmente) determinado por un Selector de etiquetas (vea a continuación las razones por las que podría querer un Servicio sin un selector).  
  
Como ejemplo, considere un backend de procesamiento de imágenes que se ejecuta con 3 réplicas. Esas réplicas son fungibles: a los frontends no les importa qué backend usan. Si bien los Pods reales que componen el conjunto de backend pueden cambiar, los clientes de frontend no deben tener en cuenta esto o realizar un seguimiento de la lista de backends. La abstracción del Servicio habilita este desacoplamiento.  
  
Para las aplicaciones nativas de Kubernetes, Kubernetes ofrece una sencilla API de puntos finales que se actualiza cada vez que cambia el conjunto de Pods en un Servicio. Para aplicaciones no nativas, Kubernetes ofrece un puente virtual basado en IP a los Servicios que redirige a los Pods back-end.
> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzYxMzg1MzEsLTEzOTc5Mzc4NDhdfQ==
-->