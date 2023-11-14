- Instalar Tekton
- Instalar tkn cli
- Componentes
- Dashboard

# Instalar Tekton en Kubernetes ( Minikube )

~~~ bash

kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

kubectl apply --filename https://storage.googleapis.com/tekton-releases/dashboard/latest/release.yaml

~~~

Verificar el estatus

~~~ bash

kubectl get pods --namespace tekton-pipelines --watch

~~~

# Mostrar dashboards

~~~ bash

kc port-forward svc/kubernetes-dashboard -n kubernetes-dashboard 8080:80

kc port-forward svc/tekton-dashboard -n tekton-pipelines 8090:9097

~~~

# Tekton hub

~~~ bash

tkn hub install task git-clone
tkn hub install task buildah
tkn hub install task kubectl-run

~~~

kc apply -f 1_TASK_HelloWorld.yaml

tkn tasks list
NAME    DESCRIPTION   AGE
hello                 11 minutes ago

tkn task start hello                          
TaskRun started: hello-run-tgsjj

In order to track the TaskRun progress run:
tkn taskrun logs hello-run-tgsjj -f -n default

tkn taskrun list  
NAME              STARTED          DURATION   STATUS
hello-run-tgsjj   30 seconds ago   5s         Succeeded
hello-run-r5p27   2 minutes ago    5s         Succeeded
hello-run-q4cs2   3 minutes ago    4s         Succeeded
hello-run-q5fdt   6 minutes ago    14s        Succeeded

tkn taskrun logs hello-run-tgsjj -f -n default

[echo] Hello World python

oc apply -f 2_TASK_GoodBye.yaml 
task.tekton.dev/goodbye created

kc apply -f 1_Pipeline_HelloGoodbye.yaml 
pipeline.tekton.dev/hello-goodbye created

tkn pipeline list  
NAME            AGE              LAST RUN   STARTED   DURATION   STATUS
hello-goodbye   46 seconds ago   ---        ---       ---        ---

tkn pipelinerun logs hello-goodbye-run-5f2dv -f -n default
[hello : echo] Hello World python

[goodbye : goodbye] Goodbye carlos!



tkn pipeline start pipeline-apiimg-ci  --use-pipelinerun  pipelinerun-apiimg-ci

oc create secret generic quaio-push \
    --from-file=.dockerconfigjson=./.dockerconfigjson \
    --type=kubernetes.io/dockerconfigjson

tkn pipeline start hello-goodbye -n pipe-hw -p username=carlosxpk


 tkn pipeline start pipeline-ci-api  --use-pipelinerun  pipelinerun-ci-api