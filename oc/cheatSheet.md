oc whoami --show-console

oc whoami --show-console
https://console-openshift-console.apps.ocp4.example.com


oc get clusterVersion

oc get clusterVersion

NAME      VERSION   AVAILABLE   PROGRESSING   SINCE   STATUS
version   4.8.57    True        False         2d2h    Cluster version is 4.8.57


oc get clusteroperators

oc get clusteroperators
NAME                                       VERSION   AVAILABLE   PROGRESSING   DEGRADED   SINCE
authentication                             4.8.57    True        False         False      2d18h
baremetal                                  4.8.57    True        False         False      2d18h
cloud-credential                           4.8.57    True        False         False      2d18h

oc get subscriptions --all-namespaces

oc get subscriptions --all-namespaces

NAMESPACE                     NAME                                   PACKAGE                                SOURCE                CHANNEL
ansible-automation-platform   ansible-automation-platform-operator   ansible-automation-platform-operator   redhat-operators      stable-2.2
openshift-operators           couchbase-enterprise-certified         couchbase-enterprise-certified         certified-operators   stable

oc adm top pods etcd-master01 -n openshift-etcd --containers

POD                       NAME                                          CPU(cores)   MEMORY(bytes)   
kube-apiserver-master01   kube-apiserver                                161m         2013Mi          
kube-apiserver-master01   kube-apiserver-check-endpoints                2m           54Mi            
kube-apiserver-master01   kube-apiserver-cert-regeneration-controller   1m           50Mi            
kube-apiserver-master01   kube-apiserver-cert-syncer                    0m           32Mi            
kube-apiserver-master01   kube-apiserver-insecure-readyz                0m           25Mi            
kube-apiserver-master01   POD                                           0m           0Mi             
                                                                        ________     ________        
                                                                        164m         2177Mi          
[student@workstation ~]$  oc adm top pods  --sum --sort-by memory --namespace openshift-kube-apiserver
NAME                      CPU(cores)   MEMORY(bytes)   
kube-apiserver-master01   164m         2177Mi          
                          ________     ________        
                          164m         2177Mi 

 oc adm top node
NAME       CPU(cores)   CPU%   MEMORY(bytes)   MEMORY%   
master01   908m         12%    10458Mi         55%   


[student@workstation ~]$ oc run -it my-app --image registry.access.redhat.com/ubi9/ubi \
> --command -- /bin/bash
Warning: would violate PodSecurity "restricted:latest": allowPrivilegeEscalation != false (container "my-app" must set securityContext.allowPrivilegeEscalation=false), unrestricted capabilities (container "my-app" must set securityContext.capabilities.drop=["ALL"]), runAsNonRoot != true (pod or container "my-app" must set securityContext.runAsNonRoot=true), seccompProfile (pod or container "my-app" must set securityContext.seccompProfile.type to "RuntimeDefault" or "Localhost")
If you don't see a command prompt, try pressing enter.
[root@my-app /]# id
uid=0(root) gid=0(root) groups=0(root)
[root@my-app /]# exit
exit
Session ended, resume using 'oc attach my-app -c my-app -i -t' command when the pod is running

[student@workstation ~]$ oc exec my-app -- date
Tue Oct 10 16:57:58 UTC 2023

[student@workstation ~]$  oc attach my-app -it
If you don't see a command prompt, try pressing enter.


oc run -it ubi9-user --restart 'Never'   --image registry.ocp4.example.com:8443/ubi9/ubi   -- /bin/bash -c "whoami && id"
1000710000
uid=1000710000(1000710000) gid=0(root) groups=0(root),1000710000

[student@workstation ~]$ oc run -it ubi9-user --restart 'Never'   --image registry.ocp4.example.com:8443/ubi9/ubi   -- /bin/bash -c "whoami && id"
Warning: would violate PodSecurity "restricted:v1.24": allowPrivilegeEscalation != false (container "ubi9-user" must set securityContext.allowPrivilegeEscalation=false), unrestricted capabilities (container "ubi9-user" must set securityContext.capabilities.drop=["ALL"]), runAsNonRoot != true (pod or container "ubi9-user" must set securityContext.runAsNonRoot=true), seccompProfile (pod or container "ubi9-user" must set securityContext.seccompProfile.type to "RuntimeDefault" or "Localhost")
root
uid=0(root) gid=0(root) groups=0(root)