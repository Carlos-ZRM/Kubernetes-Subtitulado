
Un pod (como en un pod de ballenas o guisantes) es un grupo de uno o más contenedores (como los contenedores Docker), con almacenamiento y red compartidos, y una especificación sobre cómo ejecutar los contenedores. Los contenidos de un pod siempre se colocan y se programan conjuntamente, y se ejecutan en un contexto compartido. Un pod modela un "host lógico" específico de la aplicación (contiene uno o más contenedores de aplicaciones que están relativamente estrechamente acoplados) en un mundo pre-contenedor, ejecutarse en la misma máquina virtual o física significaría ejecutarse en el mismo host lógico .  
  
Si bien Kubernetes admite más tipos de contenedor que solo Docker, Docker es el tipo más conocido, y ayuda a describir los pods en términos de Docker.  
  
El contexto compartido de un pod es un conjunto de espacios de nombres de Linux, cgroups y potencialmente otras facetas de aislamiento, las mismas cosas que aíslan un contenedor de Docker. En el contexto de un pod, las aplicaciones individuales pueden tener más sub-aislamientos aplicados.  
  
Los contenedores dentro de un pod comparten una dirección IP y espacio de puerto, y se pueden encontrar a través de localhost. También pueden comunicarse entre sí utilizando comunicaciones estándar entre procesos como los semáforos de SystemV o la memoria compartida POSIX. Los contenedores en diferentes pods tienen direcciones IP distintas y no pueden comunicarse por IPC sin una configuración especial. Estos contenedores generalmente se comunican entre sí a través de direcciones IP de Pod.  
  
Las aplicaciones dentro de un pod también tienen acceso a volúmenes compartidos, que se definen como parte de un pod y están disponibles para ser montados en el sistema de archivos de cada aplicación.  
  
En términos de construcciones de Docker, un pod se modela como un grupo de contenedores de Docker con espacios de nombres compartidos y volúmenes compartidos.  
  
Al igual que los contenedores de aplicaciones individuales, las cápsulas se consideran entidades relativamente efímeras (en lugar de duraderas). Como se discutió en la vida de un pod, los pods se crean, se les asigna una ID única (UID) y se programan en los nodos donde permanecen hasta la terminación (según la política de reinicio) o la eliminación. Si un nodo muere, los pods programados para ese nodo están programados para su eliminación, después de un período de tiempo de espera. Un pod dado (como lo define un UID) no se "reprograma" a un nuevo nodo; en su lugar, puede reemplazarse por un pod idéntico, incluso con el mismo nombre si lo desea, pero con un nuevo UID (consulte el controlador de replicación para obtener más detalles).  
  
Cuando se dice que algo tiene la misma vida útil que un pod, como un volumen, eso significa que existe mientras exista ese pod (con ese UID). Si ese pod se elimina por cualquier motivo, incluso si se crea un reemplazo idéntico, la cosa relacionada (por ejemplo, el volumen) también se destruye y se crea de nuevo.

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzOTc5Mzc4NDhdfQ==
-->