# Instalación de Kubernetes
## Ubuntu
### Aprovisionamiento
  
- Poner a Selinux en modo permisivo
- Desactivar memoria swap
```bash
setenforce 0
sudo swapoff -a
```

### Instalación de Docker
Se recomienda instalar docker desde los repositorios, ya que CE y EE mantiene Docker Swarm

```bash
apt-get install docker
systemctl enable docker.service
systemctl start docker.service
```
### Descarga y Aprovisionamiento de Kubeadm

```bash
apt-get update && apt-get install -y 

apt-transport-https curl

curl -s  https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -

cat <<EOF >/etc/apt/sources.list.d/kubernetes.list
deb https://apt.kubernetes.io/ kubernetes-xenial main
EOF

apt-get update

apt-get install -y kubelet kubeadm kubectl
apt-mark hold kubelet kubeadm kubectl
```
### Creación del cluster
 kubeadm init --pod-network-cidr=192.168.0.0/16 --apiserver-advertise-address=0.0.0.0
 mkdir -p $HOME/.kube
 sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
 sudo chown $(id -u):$(id -g) $HOME/.kube/config

 kubectl apply -f https://docs.projectcalico.org/v3.1/getting-started/kubernetes/installation/hosted/rbac-kdd.yaml
 kubectl apply -f https://docs.projectcalico.org/v3.1/getting-started/kubernetes/installation/hosted/kubernetes-datastore/calico-networking/1.7/calico.yaml
 kubectl get pods --all-namespaces

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIyNjAyNzIyMiwtMTg0MDYyMTExNSw4OT
czOTc2ODMsLTEzOTUxNDI0MTksNzMwOTk4MTE2XX0=
-->