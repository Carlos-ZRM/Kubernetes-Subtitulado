# Creación de Pipeline Hello World

- Creación namespace
- Creación de Tasks Hello y Goodbye
- Creación de Pipelines
- Ejecución

## Creación namespace

~~~ bash
oc new-project pipe-hw
~~~

~~~ bash

kubectl create namespace pipe-hw
kubectl create namespace kustom-api-dev
kubectl create namespace kustom-api-prod

kubectl config set-context --current --namespace=pipe-hw
~~~
## Creación de Tasks Hello y Goodbye

~~~ YAML
apiVersion: tekton.dev/v1beta1
kind: Task
metadata:
  name: goodbye
spec:
  params:
  - name: username
    type: string
  steps:
    - name: goodbye
      image: registry.access.redhat.com/ubi8/ubi:8.8-1067.1698056881
      script: |
        #!/bin/bash
        echo "Goodbye $(params.username)!"
~~~

Creación de tasks OpenShift

~~~ bash

oc apply -f HelloGoodbye/1_TASK_HelloWorld.yaml

oc apply -f HelloGoodbye/2_TASK_GoodBye.yaml

~~~

Creación de task K8s

~~~ bash

kubectl apply -f HelloGoodbye/1_TASK_HelloWorld.yaml

kubectl apply -f HelloGoodbye/2_TASK_GoodBye.yaml

~~~

Obtener Task creadas

~~~ bash

tkn task list -n pipe-hw

~~~

~~~

NAME      DESCRIPTION   AGE
goodbye                 1 minute ago
hello                   2 minutes ago

~~~


## Creación de Pipelines

Creación de pipeline OCP

~~~ bash
oc apply -f HelloGoodbye/1_PIPE_HelloGoodbye.yaml
~~~

Creación de pipeline k8s

~~~ bash

kubectl apply -f HelloGoodbye/1_PIPE_HelloGoodbye.yaml

~~~

Ver la pipeline creada 

~~~ bash

tkn  pipeline list
~~~

~~~ bash

NAME            AGE              LAST RUN   STARTED   DURATION   STATUS
hello-goodbye   53 seconds ago   ---        ---       ---        ---

~~~


## Ejecución

~~~ bash

tkn pipeline start hello-goodbye -n pipe-hw -p username=carlosxpk

~~~

Output

~~~ bash

PipelineRun started: hello-goodbye-run-cgnhc

In order to track the PipelineRun progress run:
tkn pipelinerun logs hello-goodbye-run-cgnhc -f -n pipe-hw
~~~

Logs

~~~ bash
tkn pipelinerun logs hello-goodbye-run-cgnhc -f -n pipe-hw

[hello : echo] Hello World

[goodbye : goodbye] Goodbye carlosxpk!

~~~

~~~ bash

tkn pipeline list


NAME            AGE              LAST RUN                  STARTED         DURATION   STATUS
hello-goodbye   17 minutes ago   hello-goodbye-run-nlnjr   8 seconds ago   ---        Running

--

NAME            AGE              LAST RUN                  STARTED          DURATION   STATUS
hello-goodbye   18 minutes ago   hello-goodbye-run-nlnjr   37 seconds ago   10s        Succeeded
~~~


~~~ bash

tkn pipelinerun list      

NAME                      STARTED         DURATION   STATUS
hello-goodbye-run-nlnjr   1 minute ago    10s        Succeeded
hello-goodbye-run-cgnhc   5 minutes ago   45s        Succeeded

~~~

oc create secret generic azureocp --from-literal=azurestorageaccountname=lvmocp \
--from-literal=azurestorageaccountkey='3Vu6b5J49BSZKlYG6JPb/WDRkHaEpkLJ/PMhKNEN6qENte4FbY2+OdRabZ4inFPj6a81Zrs9MeBT+AStoR9ZCA=='