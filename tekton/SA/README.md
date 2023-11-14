
~~~ bash
kubectl -n kube-system create serviceaccount tektonsa
~~~

~~~ bash
kubectl apply -y secret.yaml
~~~

~~~ bash

kubectl -n kube-system get secret tektonsa-token -oyaml

~~~

~~~ bash
kubectl apply  -f RBAC.yaml
~~~

~~~ bash
export USER_TOKEN_VALUE=$(kubectl -n kube-system get secret/tektonsa-token -o=go-template='{{.data.token}}' | base64 --decode)
export CURRENT_CONTEXT=$(kubectl config current-context)
export CURRENT_CLUSTER=$(kubectl config view --raw -o=go-template='{{range .contexts}}{{if eq .name "'''${CURRENT_CONTEXT}'''"}}{{ index .context "cluster" }}{{end}}{{end}}')
export CLUSTER_CA=$(kubectl config view --raw -o=go-template='{{range .clusters}}{{if eq .name "'''${CURRENT_CLUSTER}'''"}}"{{with index .cluster "certificate-authority-data" }}{{.}}{{end}}"{{ end }}{{ end }}')
export CLUSTER_SERVER=$(kubectl config view --raw -o=go-template='{{range .clusters}}{{if eq .name "'''${CURRENT_CLUSTER}'''"}}{{ .cluster.server }}{{end}}{{ end }}')
~~~

~~~ bash

kubectl create configmap kubeconfig --from-file=kubeconfig

~~~