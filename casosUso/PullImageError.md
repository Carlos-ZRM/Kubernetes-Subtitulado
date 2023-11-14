Se trata de crear una aplicación desde un Repositorio git:

oc new-app https://github.com/Carlos-ZRM/3scale_poc --context-dir=api_src --allow-missing-images --name api3scale

Se obtiene el siguiente resultado:

~~~ bash
oc new-app https://github.com/Carlos-ZRM/3scale_poc --context-dir=api_src --allow-missing-images --name api3scale

>>>

W1007 16:48:04.377008   10274 newapp.go:498] Could not find an image stream match for "ubi8/openjdk-8:1.14-14.1675788284". Make sure that a container image with that tag is available on the node for the build to succeed.
    * A Docker build using source code from https://github.com/Carlos-ZRM/3scale_poc will be created
      * The resulting image will be pushed to image stream tag "api3scale:latest"
      * Use 'oc start-build' to trigger a new build

--> Creating resources ...
    imagestream.image.openshift.io "api3scale" created
    buildconfig.build.openshift.io "api3scale" created
    deployment.apps "api3scale" created
    service "api3scale" created
--> Success
    Build scheduled, use 'oc logs -f buildconfig/api3scale' to track its progress.
    Application is not exposed. You can expose services to the outside world by executing one or more of the commands below:
     'oc expose service/api3scale' 
    Run 'oc status' to view your app.
~~~

Se ejecuta el comando mostrado para obtener los logs del build:

~~~ bash
oc logs -f buildconfig/api3scale

>>>

Cloning "https://github.com/Carlos-ZRM/3scale_poc" ...
        Commit: e7ef2048a5741aeb4fed6a016c977cd381329d65 (Update Dockerfile)
        Author: Carlos Zacarías Reyes Martínez <38059102+Carlos-ZRM@users.noreply.github.com>
        Date:   Mon Mar 13 14:59:57 2023 -0600
Replaced Dockerfile FROM image ubi8/openjdk-8:1.14-14.1675788284
Caching blobs under "/var/cache/blobs".

Pulling image ubi8/openjdk-8:1.14-14.1675788284 ...
Warning: Pull failed, retrying in 5s ...
Warning: Pull failed, retrying in 5s ...
Warning: Pull failed, retrying in 5s ...
error: build error: failed to pull image: After retrying 2 times, Pull image still failed due to error: errors:
denied: requested access to the resource is denied
unauthorized: authentication required
~~~

Se ejecutan los comandos necesarios para mostrar la información del build config, el imagestream y el build creados.


~~~ bash

oc get bc 

>>>

NAME        TYPE     FROM   LATEST
api3scale   Docker   Git    1
creyesma@creyesma-mac Documents % oc get bc api3scale -o yaml
apiVersion: build.openshift.io/v1
kind: BuildConfig
metadata:
  annotations:
    openshift.io/generated-by: OpenShiftNewApp
  creationTimestamp: "2023-10-07T22:48:05Z"
  generation: 2
  labels:
    app: api3scale
    app.kubernetes.io/component: api3scale
    app.kubernetes.io/instance: api3scale
  name: api3scale
  namespace: debug-imagestream
  resourceVersion: "1476894"
  uid: 9e45ba6a-2a4c-4270-8353-5b750d3f7456
spec:
  failedBuildsHistoryLimit: 5
  nodeSelector: null
  output:
    to:
      kind: ImageStreamTag
      name: api3scale:latest
  postCommit: {}
  resources: {}
  runPolicy: Serial
  source:
    contextDir: api_src
    git:
      uri: https://github.com/Carlos-ZRM/3scale_poc
    type: Git
  strategy:
    dockerStrategy:
      from:
        kind: DockerImage
        name: ubi8/openjdk-8:1.14-14.1675788284
    type: Docker
  successfulBuildsHistoryLimit: 5
  triggers:
  - github:
      secret: nzrFXzSjYB1xq8BsPXtD
    type: GitHub
  - generic:
      secret: Xtngj6GBfNcn42FS0fqE
    type: Generic
  - type: ConfigChange
status:
  lastVersion: 1

~~~

~~~ bash

oc get is                                                                                                        
>>>

NAME        IMAGE REPOSITORY                                                               TAGS   UPDATED
api3scale   image-registry.openshift-image-registry.svc:5000/debug-imagestream/api3scale          

oc get is  api3scale -o yaml

>>>

apiVersion: image.openshift.io/v1
kind: ImageStream
metadata:
  annotations:
    openshift.io/generated-by: OpenShiftNewApp
  creationTimestamp: "2023-10-07T22:48:04Z"
  generation: 1
  labels:
    app: api3scale
    app.kubernetes.io/component: api3scale
    app.kubernetes.io/instance: api3scale
  name: api3scale
  namespace: debug-imagestream
  resourceVersion: "1476889"
  uid: 1058dceb-7f15-4f12-8bbb-790e03e6d218
spec:
  lookupPolicy:
    local: false
status:
  dockerImageRepository: image-registry.openshift-image-registry.svc:5000/debug-imagestream/api3scale
~~~

Se intenta importar la imagen de forma manual 

~~~ bash

oc import-image  ubi8/openjdk-8:1.14-14.1675788284  --confirm  

error: tag 1.14-14.1675788284 failed: you may not have access to the container image "docker.io/ubi8/openjdk-8:1.14-14.1675788284"
imagestream.image.openshift.io/openjdk-8 imported with errors

Name:                   openjdk-8
Namespace:              debug-imagestream
Created:                10 seconds ago
Labels:                 <none>
Annotations:            openshift.io/image.dockerRepositoryCheck=2023-10-07T22:54:23Z
Image Repository:       image-registry.openshift-image-registry.svc:5000/debug-imagestream/openjdk-8
Image Lookup:           local=false
Unique Images:          0
Tags:                   1

1.14-14.1675788284
  tagged from ubi8/openjdk-8:1.14-14.1675788284

  ! error: Import failed (Unauthorized): you may not have access to the container image "docker.io/ubi8/openjdk-8:1.14-14.1675788284"
      10 seconds ago
~~~

Por lo que agregamos el 

Nos damos cuenta que intenta acceder a ***docker.io*** para hacer el pull de la imagen por lo que revisamos la configuración de los registries en OpenShift

~~~ bash
oc get image.config.openshift.io/cluster  -o yaml

>>>


apiVersion: config.openshift.io/v1
kind: Image
metadata:
  annotations:
    include.release.openshift.io/ibm-cloud-managed: "true"
    include.release.openshift.io/self-managed-high-availability: "true"
    include.release.openshift.io/single-node-developer: "true"
    release.openshift.io/create-only: "true"
  creationTimestamp: "2023-10-05T01:41:17Z"
  generation: 1
  name: cluster
  resourceVersion: "25192"
  uid: 2bd9b620-7063-40e6-a92f-d9a0670a6288
spec: {}
status:
  internalRegistryHostname: image-registry.openshift-image-registry.svc:5000
~~~

~~~

spec: 
  registrySources:
    allowedRegistries:
     - quay.io
     - registry.redhat.io
~~~

Por lo que se desea agregar el registry a la lista de registries 