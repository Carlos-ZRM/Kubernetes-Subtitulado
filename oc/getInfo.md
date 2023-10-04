### Get Cluster Version
~~~ bash
creyesma@creyesma-mac Kubernetes-Subtitulado % oc get clusterVersion
NAME      VERSION   AVAILABLE   PROGRESSING   SINCE   STATUS
version   4.11.47   True        False         8d      Cluster version is 4.11.47

~~~

### Get Uster
~~~ bash
creyesma@creyesma-mac Kubernetes-Subtitulado % oc whoami 
kube:admin
~~~

### Get Cluster Infi
~~~ bash
creyesma@creyesma-mac Kubernetes-Subtitulado %  oc cluster-info
Kubernetes control plane is running at https://api.shrocp4upi411ovn.lab.psi.pnq2.redhat.com:6443

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
~~~

### Get Cluster operators
~~~ bash

creyesma@creyesma-mac Kubernetes-Subtitulado % oc get clusteroperator
NAME                                       VERSION   AVAILABLE   PROGRESSING   DEGRADED   SINCE   MESSAGE
authentication                             4.11.47   True        False         False      2d17h   
baremetal                                  4.11.47   True        False         False      10d     
cloud-controller-manager                   4.11.47   True        False         False      10d     
cloud-credential                           4.11.47   True        False         False      10d     
cluster-autoscaler                         4.11.47   True        False         False      10d     
config-operator                            4.11.47   True        False         False      10d     
console                                    4.11.47   True        False         False      2d17h   
csi-snapshot-controller                    4.11.47   True        False         False      10d     
dns                                        4.11.47   True        False         False      10d     
etcd                                       4.11.47   True        False         False      10d     
image-registry                             4.11.47   True        False         False      10d     
ingress                                    4.11.47   True        False         False      2d17h   
insights                                   4.11.47   True        False         False      10d     
kube-apiserver                             4.11.47   True        False         False      10d     
kube-controller-manager                    4.11.47   True        False         False      10d     
kube-scheduler                             4.11.47   True        False         False      10d     
kube-storage-version-migrator              4.11.47   True        False         False      10d     
machine-api                                4.11.47   True        False         False      10d     
machine-approver                           4.11.47   True        False         False      10d     
machine-config                             4.11.47   True        False         False      10d     
marketplace                                4.11.47   True        False         False      10d     
monitoring                                 4.11.47   True        False         False      2d17h   
network                                    4.11.47   True        True          False      10d     DaemonSet "/openshift-network-diagnostics/network-check-target" is not available (awaiting 1 nodes)
node-tuning                                4.11.47   True        False         False      10d     
openshift-apiserver                        4.11.47   True        False         False      10d     
openshift-controller-manager               4.11.47   True        False         False      9d      
openshift-samples                          4.11.47   True        False         False      10d     
operator-lifecycle-manager                 4.11.47   True        False         False      10d     
operator-lifecycle-manager-catalog         4.11.47   True        False         False      10d     
operator-lifecycle-manager-packageserver   4.11.47   True        False         False      10d     
service-ca                                 4.11.47   True        False         False      10d     
storage                                    4.11.47   True        False         False      10d
~~~

### Get api-versions of the objects

~~~ bash
creyesma@creyesma-mac Kubernetes-Subtitulado % oc api-versions
admissionregistration.k8s.io/v1
apiextensions.k8s.io/v1
apiregistration.k8s.io/v1
apiserver.openshift.io/v1
app.redislabs.com/v1
app.redislabs.com/v1alpha1
apps.openshift.io/v1
apps/v1
argoproj.io/v1alpha1
authentication.k8s.io/v1
authorization.k8s.io/v1
authorization.openshift.io/v1
autoscaling.openshift.io/v1
autoscaling.openshift.io/v1beta1
autoscaling/v1
autoscaling/v2
autoscaling/v2beta1
autoscaling/v2beta2
batch/v1
batch/v1beta1
build.openshift.io/v1
cdi.kubevirt.io/v1alpha1
cdi.kubevirt.io/v1beta1
ceph.rook.io/v1
certificates.k8s.io/v1
cloudcredential.openshift.io/v1
compliance.openshift.io/v1alpha1
config.openshift.io/v1
console.openshift.io/v1
console.openshift.io/v1alpha1
controlplane.operator.openshift.io/v1alpha1
coordination.k8s.io/v1
csiaddons.openshift.io/v1alpha1
discovery.k8s.io/v1
discovery.k8s.io/v1beta1
events.k8s.io/v1
events.k8s.io/v1beta1
flowcontrol.apiserver.k8s.io/v1beta1
flowcontrol.apiserver.k8s.io/v1beta2
hco.kubevirt.io/v1beta1
helm.openshift.io/v1beta1
hostpathprovisioner.kubevirt.io/v1alpha1
hostpathprovisioner.kubevirt.io/v1beta1
image.openshift.io/v1
imageregistry.operator.openshift.io/v1
ingress.operator.openshift.io/v1
k8s.cni.cncf.io/v1
k8s.ovn.org/v1
kubevirt.io/v1
kubevirt.io/v1alpha3
local.storage.openshift.io/v1
local.storage.openshift.io/v1alpha1
machine.openshift.io/v1beta1
machineconfiguration.openshift.io/v1
maistra.io/v1
maistra.io/v2
metal3.io/v1alpha1
metrics.k8s.io/v1beta1
migration.k8s.io/v1alpha1
monitoring.coreos.com/v1
monitoring.coreos.com/v1alpha1
monitoring.coreos.com/v1beta1
network.operator.openshift.io/v1
networkaddonsoperator.network.kubevirt.io/v1
networkaddonsoperator.network.kubevirt.io/v1alpha1
networking.k8s.io/v1
nmstate.io/v1
nmstate.io/v1beta1
node.k8s.io/v1
node.k8s.io/v1beta1
noobaa.io/v1alpha1
oauth.openshift.io/v1
objectbucket.io/v1alpha1
ocs.openshift.io/v1
ocs.openshift.io/v1alpha1
odf.openshift.io/v1alpha1
operator.openshift.io/v1
operator.openshift.io/v1alpha1
operators.coreos.com/v1
operators.coreos.com/v1alpha1
operators.coreos.com/v1alpha2
operators.coreos.com/v2
packages.operators.coreos.com/v1
performance.openshift.io/v1
performance.openshift.io/v1alpha1
performance.openshift.io/v2
pipelines.openshift.io/v1alpha1
policy/v1
policy/v1beta1
project.openshift.io/v1
pxc.percona.com/v1
pxc.percona.com/v1-10-0
pxc.percona.com/v1-11-0
quota.openshift.io/v1
rbac.authorization.k8s.io/v1
replication.storage.openshift.io/v1alpha1
route.openshift.io/v1
samples.operator.openshift.io/v1
scheduling.k8s.io/v1
security.internal.openshift.io/v1
security.openshift.io/v1
snapshot.storage.k8s.io/v1
ssp.kubevirt.io/v1beta1
storage.k8s.io/v1
storage.k8s.io/v1beta1
tektontasks.kubevirt.io/v1alpha1
template.openshift.io/v1
tuned.openshift.io/v1
user.openshift.io/v1
v1
whereabouts.cni.cncf.io/v1alpha1
~~~

### Get Console URL

~~~ bash
creyesma@creyesma-mac Kubernetes-Subtitulado % oc whoami --show-console
https://console-openshift-console.apps.shrocp4upi411ovn.lab.psi.pnq2.redhat.com
~~~

### Get Status
~~~ bash
creyesma@creyesma-mac Kubernetes-Subtitulado % oc status
In project default on server https://api.shrocp4upi411ovn.lab.psi.pnq2.redhat.com:6443

svc/openshift - kubernetes.default.svc.cluster.local
svc/kubernetes - 172.30.0.1:443 -> 6443

View details with 'oc describe <resource>/<name>' or list resources with 'oc get all'
~~~

### Get project status

~~~ bash
creyesma@creyesma-mac Kubernetes-Subtitulado %  oc status -n openshift-authentication
In project openshift-authentication on server https://api.shrocp4upi411ovn.lab.psi.pnq2.redhat.com:6443

https://oauth-openshift.apps.shrocp4upi411ovn.lab.psi.pnq2.redhat.com (passthrough) to pod port 6443 (svc/oauth-openshift)
  deployment/oauth-openshift deploys quay.io/openshift-release-dev/ocp-v4.0-art-dev@sha256:e381a4bd25bd4f7bf0ae7c886cd63275f1cb8b444c8bb7ae717f1099acb586e3
    deployment #7 running for 5 days - 3 pods
    deployment #6 deployed 5 days ago
    deployment #5 deployed 8 days ago
    deployment #4 deployed 8 days ago
    deployment #3 deployed 10 days ago
    deployment #2 deployed 10 days ago
    deployment #1 deployed 10 days ago

33 warnings identified, use 'oc status --suggest' to see details.
~~~
### Get api objects
~~~ bash
creyesma@creyesma-mac Kubernetes-Subtitulado % oc api-resources
NAME                                   SHORTNAMES                         APIVERSION                                     NAMESPACED   KIND
bindings                                                                  v1                                             true         Binding
componentstatuses                      cs                                 v1                                             false        ComponentStatus
configmaps                             cm                                 v1                                             true         ConfigMap
endpoints                              ep                                 v1                                             true         Endpoints
events                                 ev                                 v1                                             true         Event
limitranges                            limits                             v1                                             true         LimitRange
namespaces                             ns                                 v1                                             false        Namespace
nodes                                  no                                 v1                                             false        Node
persistentvolumeclaims                 pvc                                v1                                             true         PersistentVolumeClaim
persistentvolumes                      pv                                 v1                                             false        PersistentVolume
pods                                   po                                 v1                                             true         Pod
podtemplates                                                              v1                                             true         PodTemplate
replicationcontrollers                 rc                                 v1                                             true         ReplicationController
resourcequotas                         quota                              v1                                             true         ResourceQuota
secrets                                                                   v1                                             true         Secret
serviceaccounts                        sa                                 v1                                             true         ServiceAccount
services                               svc                                v1                                             true         Service
mutatingwebhookconfigurations                                             admissionregistration.k8s.io/v1                false        MutatingWebhookConfiguration
validatingwebhookconfigurations                                           admissionregistration.k8s.io/v1                false        ValidatingWebhookConfiguration
customresourcedefinitions              crd,crds                           apiextensions.k8s.io/v1                        false        CustomResourceDefinition
apiservices                                                               apiregistration.k8s.io/v1                      false        APIService
apirequestcounts                                                          apiserver.openshift.io/v1                      false        APIRequestCount
redisenterpriseactiveactivedatabases   reaadb                             app.redislabs.com/v1alpha1                     true         RedisEnterpriseActiveActiveDatabase
redisenterpriseclusters                rec                                app.redislabs.com/v1                           true         RedisEnterpriseCluster
redisenterprisedatabases               redb                               app.redislabs.com/v1alpha1                     true         RedisEnterpriseDatabase
redisenterpriseremoteclusters          rerc                               app.redislabs.com/v1alpha1                     true         RedisEnterpriseRemoteCluster
controllerrevisions                                                       apps/v1                                        true         ControllerRevision
daemonsets                             ds                                 apps/v1                                        true         DaemonSet
deployments                            deploy                             apps/v1                                        true         Deployment
replicasets                            rs                                 apps/v1                                        true         ReplicaSet
statefulsets                           sts                                apps/v1                                        true         StatefulSet
deploymentconfigs                      dc                                 apps.openshift.io/v1                           true         DeploymentConfig
applications                           app,apps                           argoproj.io/v1alpha1                           true         Application
applicationsets                        appset,appsets                     argoproj.io/v1alpha1                           true         ApplicationSet
appprojects                            appproj,appprojs                   argoproj.io/v1alpha1                           true         AppProject
argocds                                                                   argoproj.io/v1alpha1                           true         ArgoCD
tokenreviews                                                              authentication.k8s.io/v1                       false        TokenReview
localsubjectaccessreviews                                                 authorization.k8s.io/v1                        true         LocalSubjectAccessReview
selfsubjectaccessreviews                                                  authorization.k8s.io/v1                        false        SelfSubjectAccessReview
selfsubjectrulesreviews                                                   authorization.k8s.io/v1                        false        SelfSubjectRulesReview
subjectaccessreviews                                                      authorization.k8s.io/v1                        false        SubjectAccessReview
clusterrolebindings                                                       authorization.openshift.io/v1                  false        ClusterRoleBinding
clusterroles                                                              authorization.openshift.io/v1                  false        ClusterRole
localresourceaccessreviews                                                authorization.openshift.io/v1                  true         LocalResourceAccessReview
localsubjectaccessreviews                                                 authorization.openshift.io/v1                  true         LocalSubjectAccessReview
resourceaccessreviews                                                     authorization.openshift.io/v1                  false        ResourceAccessReview
rolebindingrestrictions                                                   authorization.openshift.io/v1                  true         RoleBindingRestriction
rolebindings                                                              authorization.openshift.io/v1                  true         RoleBinding
roles                                                                     authorization.openshift.io/v1                  true         Role
selfsubjectrulesreviews                                                   authorization.openshift.io/v1                  true         SelfSubjectRulesReview
subjectaccessreviews                                                      authorization.openshift.io/v1                  false        SubjectAccessReview
subjectrulesreviews                                                       authorization.openshift.io/v1                  true         SubjectRulesReview
horizontalpodautoscalers               hpa                                autoscaling/v2                                 true         HorizontalPodAutoscaler
clusterautoscalers                     ca                                 autoscaling.openshift.io/v1                    false        ClusterAutoscaler
machineautoscalers                     ma                                 autoscaling.openshift.io/v1beta1               true         MachineAutoscaler
cronjobs                               cj                                 batch/v1                                       true         CronJob
jobs                                                                      batch/v1                                       true         Job
buildconfigs                           bc                                 build.openshift.io/v1                          true         BuildConfig
builds                                                                    build.openshift.io/v1                          true         Build
cdis                                   cdi,cdis                           cdi.kubevirt.io/v1beta1                        false        CDI
cephblockpoolradosnamespaces                                              ceph.rook.io/v1                                true         CephBlockPoolRadosNamespace
cephblockpools                                                            ceph.rook.io/v1                                true         CephBlockPool
cephbucketnotifications                                                   ceph.rook.io/v1                                true         CephBucketNotification
cephbuckettopics                                                          ceph.rook.io/v1                                true         CephBucketTopic
cephclients                                                               ceph.rook.io/v1                                true         CephClient
cephclusters                                                              ceph.rook.io/v1                                true         CephCluster
cephfilesystemmirrors                                                     ceph.rook.io/v1                                true         CephFilesystemMirror
cephfilesystems                                                           ceph.rook.io/v1                                true         CephFilesystem
cephfilesystemsubvolumegroups                                             ceph.rook.io/v1                                true         CephFilesystemSubVolumeGroup
cephnfses                              nfs                                ceph.rook.io/v1                                true         CephNFS
cephobjectrealms                                                          ceph.rook.io/v1                                true         CephObjectRealm
cephobjectstores                                                          ceph.rook.io/v1                                true         CephObjectStore
cephobjectstoreusers                   rcou,objectuser                    ceph.rook.io/v1                                true         CephObjectStoreUser
cephobjectzonegroups                                                      ceph.rook.io/v1                                true         CephObjectZoneGroup
cephobjectzones                                                           ceph.rook.io/v1                                true         CephObjectZone
cephrbdmirrors                                                            ceph.rook.io/v1                                true         CephRBDMirror
certificatesigningrequests             csr                                certificates.k8s.io/v1                         false        CertificateSigningRequest
credentialsrequests                                                       cloudcredential.openshift.io/v1                true         CredentialsRequest
compliancecheckresults                 ccr,checkresults,checkresult       compliance.openshift.io/v1alpha1               true         ComplianceCheckResult
complianceremediations                 cr,remediations,remediation,rems   compliance.openshift.io/v1alpha1               true         ComplianceRemediation
compliancescans                        scans,scan                         compliance.openshift.io/v1alpha1               true         ComplianceScan
compliancesuites                       suites,suite                       compliance.openshift.io/v1alpha1               true         ComplianceSuite
profilebundles                         pb                                 compliance.openshift.io/v1alpha1               true         ProfileBundle
profiles                               profs,prof                         compliance.openshift.io/v1alpha1               true         Profile
rules                                                                     compliance.openshift.io/v1alpha1               true         Rule
scansettingbindings                    ssb                                compliance.openshift.io/v1alpha1               true         ScanSettingBinding
scansettings                           ss                                 compliance.openshift.io/v1alpha1               true         ScanSetting
tailoredprofiles                       tp,tprof                           compliance.openshift.io/v1alpha1               true         TailoredProfile
variables                              var                                compliance.openshift.io/v1alpha1               true         Variable
apiservers                                                                config.openshift.io/v1                         false        APIServer
authentications                                                           config.openshift.io/v1                         false        Authentication
builds                                                                    config.openshift.io/v1                         false        Build
clusteroperators                       co                                 config.openshift.io/v1                         false        ClusterOperator
clusterversions                                                           config.openshift.io/v1                         false        ClusterVersion
consoles                                                                  config.openshift.io/v1                         false        Console
dnses                                                                     config.openshift.io/v1                         false        DNS
featuregates                                                              config.openshift.io/v1                         false        FeatureGate
imagecontentpolicies                                                      config.openshift.io/v1                         false        ImageContentPolicy
images                                                                    config.openshift.io/v1                         false        Image
infrastructures                                                           config.openshift.io/v1                         false        Infrastructure
ingresses                                                                 config.openshift.io/v1                         false        Ingress
networks                                                                  config.openshift.io/v1                         false        Network
nodes                                                                     config.openshift.io/v1                         false        Node
oauths                                                                    config.openshift.io/v1                         false        OAuth
operatorhubs                                                              config.openshift.io/v1                         false        OperatorHub
projects                                                                  config.openshift.io/v1                         false        Project
proxies                                                                   config.openshift.io/v1                         false        Proxy
schedulers                                                                config.openshift.io/v1                         false        Scheduler
consoleclidownloads                                                       console.openshift.io/v1                        false        ConsoleCLIDownload
consoleexternalloglinks                                                   console.openshift.io/v1                        false        ConsoleExternalLogLink
consolelinks                                                              console.openshift.io/v1                        false        ConsoleLink
consolenotifications                                                      console.openshift.io/v1                        false        ConsoleNotification
consoleplugins                                                            console.openshift.io/v1alpha1                  false        ConsolePlugin
consolequickstarts                                                        console.openshift.io/v1                        false        ConsoleQuickStart
consoleyamlsamples                                                        console.openshift.io/v1                        false        ConsoleYAMLSample
podnetworkconnectivitychecks                                              controlplane.operator.openshift.io/v1alpha1    true         PodNetworkConnectivityCheck
leases                                                                    coordination.k8s.io/v1                         true         Lease
csiaddonsnodes                                                            csiaddons.openshift.io/v1alpha1                true         CSIAddonsNode
networkfences                                                             csiaddons.openshift.io/v1alpha1                false        NetworkFence
reclaimspacecronjobs                                                      csiaddons.openshift.io/v1alpha1                true         ReclaimSpaceCronJob
reclaimspacejobs                                                          csiaddons.openshift.io/v1alpha1                true         ReclaimSpaceJob
endpointslices                                                            discovery.k8s.io/v1                            true         EndpointSlice
events                                 ev                                 events.k8s.io/v1                               true         Event
flowschemas                                                               flowcontrol.apiserver.k8s.io/v1beta2           false        FlowSchema
prioritylevelconfigurations                                               flowcontrol.apiserver.k8s.io/v1beta2           false        PriorityLevelConfiguration
hyperconvergeds                        hco,hcos                           hco.kubevirt.io/v1beta1                        true         HyperConverged
helmchartrepositories                                                     helm.openshift.io/v1beta1                      false        HelmChartRepository
projecthelmchartrepositories                                              helm.openshift.io/v1beta1                      true         ProjectHelmChartRepository
hostpathprovisioners                                                      hostpathprovisioner.kubevirt.io/v1beta1        false        HostPathProvisioner
images                                                                    image.openshift.io/v1                          false        Image
imagesignatures                                                           image.openshift.io/v1                          false        ImageSignature
imagestreamimages                      isimage                            image.openshift.io/v1                          true         ImageStreamImage
imagestreamimports                                                        image.openshift.io/v1                          true         ImageStreamImport
imagestreammappings                                                       image.openshift.io/v1                          true         ImageStreamMapping
imagestreams                           is                                 image.openshift.io/v1                          true         ImageStream
imagestreamtags                        istag                              image.openshift.io/v1                          true         ImageStreamTag
imagetags                              itag                               image.openshift.io/v1                          true         ImageTag
configs                                                                   imageregistry.operator.openshift.io/v1         false        Config
imagepruners                                                              imageregistry.operator.openshift.io/v1         false        ImagePruner
dnsrecords                                                                ingress.operator.openshift.io/v1               true         DNSRecord
network-attachment-definitions         net-attach-def                     k8s.cni.cncf.io/v1                             true         NetworkAttachmentDefinition
egressfirewalls                                                           k8s.ovn.org/v1                                 true         EgressFirewall
egressips                              eip                                k8s.ovn.org/v1                                 false        EgressIP
egressqoses                                                               k8s.ovn.org/v1                                 true         EgressQoS
kubevirts                              kv,kvs                             kubevirt.io/v1                                 true         KubeVirt
localvolumediscoveries                                                    local.storage.openshift.io/v1alpha1            true         LocalVolumeDiscovery
localvolumediscoveryresults                                               local.storage.openshift.io/v1alpha1            true         LocalVolumeDiscoveryResult
localvolumes                                                              local.storage.openshift.io/v1                  true         LocalVolume
localvolumesets                        lvset,lvsets                       local.storage.openshift.io/v1alpha1            true         LocalVolumeSet
machinehealthchecks                    mhc,mhcs                           machine.openshift.io/v1beta1                   true         MachineHealthCheck
machines                                                                  machine.openshift.io/v1beta1                   true         Machine
machinesets                                                               machine.openshift.io/v1beta1                   true         MachineSet
containerruntimeconfigs                ctrcfg                             machineconfiguration.openshift.io/v1           false        ContainerRuntimeConfig
controllerconfigs                                                         machineconfiguration.openshift.io/v1           false        ControllerConfig
kubeletconfigs                                                            machineconfiguration.openshift.io/v1           false        KubeletConfig
machineconfigpools                     mcp                                machineconfiguration.openshift.io/v1           false        MachineConfigPool
machineconfigs                         mc                                 machineconfiguration.openshift.io/v1           false        MachineConfig
servicemeshcontrolplanes               smcp                               maistra.io/v2                                  true         ServiceMeshControlPlane
servicemeshmemberrolls                 smmr                               maistra.io/v1                                  true         ServiceMeshMemberRoll
servicemeshmembers                     smm                                maistra.io/v1                                  true         ServiceMeshMember
baremetalhosts                         bmh,bmhost                         metal3.io/v1alpha1                             true         BareMetalHost
bmceventsubscriptions                  bes,bmcevent                       metal3.io/v1alpha1                             true         BMCEventSubscription
firmwareschemas                                                           metal3.io/v1alpha1                             true         FirmwareSchema
hostfirmwaresettings                   hfs                                metal3.io/v1alpha1                             true         HostFirmwareSettings
preprovisioningimages                  ppimg                              metal3.io/v1alpha1                             true         PreprovisioningImage
provisionings                                                             metal3.io/v1alpha1                             false        Provisioning
nodes                                                                     metrics.k8s.io/v1beta1                         false        NodeMetrics
pods                                                                      metrics.k8s.io/v1beta1                         true         PodMetrics
storagestates                                                             migration.k8s.io/v1alpha1                      false        StorageState
storageversionmigrations                                                  migration.k8s.io/v1alpha1                      false        StorageVersionMigration
alertmanagerconfigs                    amcfg                              monitoring.coreos.com/v1beta1                  true         AlertmanagerConfig
alertmanagers                          am                                 monitoring.coreos.com/v1                       true         Alertmanager
podmonitors                            pmon                               monitoring.coreos.com/v1                       true         PodMonitor
probes                                 prb                                monitoring.coreos.com/v1                       true         Probe
prometheuses                           prom                               monitoring.coreos.com/v1                       true         Prometheus
prometheusrules                        promrule                           monitoring.coreos.com/v1                       true         PrometheusRule
servicemonitors                        smon                               monitoring.coreos.com/v1                       true         ServiceMonitor
thanosrulers                           ruler                              monitoring.coreos.com/v1                       true         ThanosRuler
egressrouters                                                             network.operator.openshift.io/v1               true         EgressRouter
operatorpkis                                                              network.operator.openshift.io/v1               true         OperatorPKI
networkaddonsconfigs                                                      networkaddonsoperator.network.kubevirt.io/v1   false        NetworkAddonsConfig
ingressclasses                                                            networking.k8s.io/v1                           false        IngressClass
ingresses                              ing                                networking.k8s.io/v1                           true         Ingress
networkpolicies                        netpol                             networking.k8s.io/v1                           true         NetworkPolicy
nmstates                                                                  nmstate.io/v1                                  false        NMState
runtimeclasses                                                            node.k8s.io/v1                                 false        RuntimeClass
backingstores                                                             noobaa.io/v1alpha1                             true         BackingStore
bucketclasses                                                             noobaa.io/v1alpha1                             true         BucketClass
namespacestores                                                           noobaa.io/v1alpha1                             true         NamespaceStore
noobaaaccounts                                                            noobaa.io/v1alpha1                             true         NooBaaAccount
noobaas                                nb                                 noobaa.io/v1alpha1                             true         NooBaa
oauthaccesstokens                                                         oauth.openshift.io/v1                          false        OAuthAccessToken
oauthauthorizetokens                                                      oauth.openshift.io/v1                          false        OAuthAuthorizeToken
oauthclientauthorizations                                                 oauth.openshift.io/v1                          false        OAuthClientAuthorization
oauthclients                                                              oauth.openshift.io/v1                          false        OAuthClient
tokenreviews                                                              oauth.openshift.io/v1                          false        TokenReview
useroauthaccesstokens                                                     oauth.openshift.io/v1                          false        UserOAuthAccessToken
objectbucketclaims                     obc,obcs                           objectbucket.io/v1alpha1                       true         ObjectBucketClaim
objectbuckets                          ob,obs                             objectbucket.io/v1alpha1                       false        ObjectBucket
ocsinitializations                                                        ocs.openshift.io/v1                            true         OCSInitialization
storageclassclaims                                                        ocs.openshift.io/v1alpha1                      true         StorageClassClaim
storageclusters                                                           ocs.openshift.io/v1                            true         StorageCluster
storageconsumers                                                          ocs.openshift.io/v1alpha1                      true         StorageConsumer
storagesystems                         storsys                            odf.openshift.io/v1alpha1                      true         StorageSystem
authentications                                                           operator.openshift.io/v1                       false        Authentication
cloudcredentials                                                          operator.openshift.io/v1                       false        CloudCredential
clustercsidrivers                                                         operator.openshift.io/v1                       false        ClusterCSIDriver
configs                                                                   operator.openshift.io/v1                       false        Config
consoles                                                                  operator.openshift.io/v1                       false        Console
csisnapshotcontrollers                                                    operator.openshift.io/v1                       false        CSISnapshotController
dnses                                                                     operator.openshift.io/v1                       false        DNS
etcds                                                                     operator.openshift.io/v1                       false        Etcd
imagecontentsourcepolicies                                                operator.openshift.io/v1alpha1                 false        ImageContentSourcePolicy
ingresscontrollers                                                        operator.openshift.io/v1                       true         IngressController
kubeapiservers                                                            operator.openshift.io/v1                       false        KubeAPIServer
kubecontrollermanagers                                                    operator.openshift.io/v1                       false        KubeControllerManager
kubeschedulers                                                            operator.openshift.io/v1                       false        KubeScheduler
kubestorageversionmigrators                                               operator.openshift.io/v1                       false        KubeStorageVersionMigrator
networks                                                                  operator.openshift.io/v1                       false        Network
openshiftapiservers                                                       operator.openshift.io/v1                       false        OpenShiftAPIServer
openshiftcontrollermanagers                                               operator.openshift.io/v1                       false        OpenShiftControllerManager
servicecas                                                                operator.openshift.io/v1                       false        ServiceCA
storages                                                                  operator.openshift.io/v1                       false        Storage
catalogsources                         catsrc                             operators.coreos.com/v1alpha1                  true         CatalogSource
clusterserviceversions                 csv,csvs                           operators.coreos.com/v1alpha1                  true         ClusterServiceVersion
installplans                           ip                                 operators.coreos.com/v1alpha1                  true         InstallPlan
olmconfigs                                                                operators.coreos.com/v1                        false        OLMConfig
operatorconditions                     condition                          operators.coreos.com/v2                        true         OperatorCondition
operatorgroups                         og                                 operators.coreos.com/v1                        true         OperatorGroup
operators                                                                 operators.coreos.com/v1                        false        Operator
subscriptions                          sub,subs                           operators.coreos.com/v1alpha1                  true         Subscription
packagemanifests                                                          packages.operators.coreos.com/v1               true         PackageManifest
performanceprofiles                                                       performance.openshift.io/v2                    false        PerformanceProfile
gitopsservices                                                            pipelines.openshift.io/v1alpha1                false        GitopsService
poddisruptionbudgets                   pdb                                policy/v1                                      true         PodDisruptionBudget
podsecuritypolicies                    psp                                policy/v1beta1                                 false        PodSecurityPolicy
projectrequests                                                           project.openshift.io/v1                        false        ProjectRequest
projects                                                                  project.openshift.io/v1                        false        Project
perconaxtradbclusterbackups            pxc-backup,pxc-backups             pxc.percona.com/v1                             true         PerconaXtraDBClusterBackup
perconaxtradbclusterrestores           pxc-restore,pxc-restores           pxc.percona.com/v1                             true         PerconaXtraDBClusterRestore
perconaxtradbclusters                  pxc,pxcs                           pxc.percona.com/v1                             true         PerconaXtraDBCluster
appliedclusterresourcequotas                                              quota.openshift.io/v1                          true         AppliedClusterResourceQuota
clusterresourcequotas                  clusterquota                       quota.openshift.io/v1                          false        ClusterResourceQuota
clusterrolebindings                                                       rbac.authorization.k8s.io/v1                   false        ClusterRoleBinding
clusterroles                                                              rbac.authorization.k8s.io/v1                   false        ClusterRole
rolebindings                                                              rbac.authorization.k8s.io/v1                   true         RoleBinding
roles                                                                     rbac.authorization.k8s.io/v1                   true         Role
volumereplicationclasses               vrc                                replication.storage.openshift.io/v1alpha1      false        VolumeReplicationClass
volumereplications                     vr                                 replication.storage.openshift.io/v1alpha1      true         VolumeReplication
routes                                                                    route.openshift.io/v1                          true         Route
configs                                                                   samples.operator.openshift.io/v1               false        Config
priorityclasses                        pc                                 scheduling.k8s.io/v1                           false        PriorityClass
rangeallocations                                                          security.internal.openshift.io/v1              false        RangeAllocation
podsecuritypolicyreviews                                                  security.openshift.io/v1                       true         PodSecurityPolicyReview
podsecuritypolicyselfsubjectreviews                                       security.openshift.io/v1                       true         PodSecurityPolicySelfSubjectReview
podsecuritypolicysubjectreviews                                           security.openshift.io/v1                       true         PodSecurityPolicySubjectReview
rangeallocations                                                          security.openshift.io/v1                       false        RangeAllocation
securitycontextconstraints             scc                                security.openshift.io/v1                       false        SecurityContextConstraints
volumesnapshotclasses                  vsclass,vsclasses                  snapshot.storage.k8s.io/v1                     false        VolumeSnapshotClass
volumesnapshotcontents                 vsc,vscs                           snapshot.storage.k8s.io/v1                     false        VolumeSnapshotContent
volumesnapshots                        vs                                 snapshot.storage.k8s.io/v1                     true         VolumeSnapshot
ssps                                                                      ssp.kubevirt.io/v1beta1                        true         SSP
csidrivers                                                                storage.k8s.io/v1                              false        CSIDriver
csinodes                                                                  storage.k8s.io/v1                              false        CSINode
csistoragecapacities                                                      storage.k8s.io/v1                              true         CSIStorageCapacity
storageclasses                         sc                                 storage.k8s.io/v1                              false        StorageClass
volumeattachments                                                         storage.k8s.io/v1                              false        VolumeAttachment
tektontasks                                                               tektontasks.kubevirt.io/v1alpha1               true         TektonTasks
brokertemplateinstances                                                   template.openshift.io/v1                       false        BrokerTemplateInstance
processedtemplates                                                        template.openshift.io/v1                       true         Template
templateinstances                                                         template.openshift.io/v1                       true         TemplateInstance
templates                                                                 template.openshift.io/v1                       true         Template
profiles                                                                  tuned.openshift.io/v1                          true         Profile
tuneds                                                                    tuned.openshift.io/v1                          true         Tuned
groups                                                                    user.openshift.io/v1                           false        Group
identities                                                                user.openshift.io/v1                           false        Identity
useridentitymappings                                                      user.openshift.io/v1                           false        UserIdentityMapping
users                                                                     user.openshift.io/v1                           false        User
ippools                                                                   whereabouts.cni.cncf.io/v1alpha1               true         IPPool
overlappingrangeipreservations                                            whereabouts.cni.cncf.io/v1alpha1               true         OverlappingRangeIPReservatio
~~~