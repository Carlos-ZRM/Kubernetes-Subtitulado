oc import-image  ubi8/openjdk-8:1.14-14.1675788284 --from=registry.access.redhat.com/ubi8/openjdk-8:1.17-1.1693366248 --confirm 

oc new-app https://github.com/Carlos-ZRM/3scale_poc --context-dir=api_src --allow-missing-images --name api3scale

oc new-app https://github.com/Carlos-ZRM/3scale_poc#python-api-img --context-dir=apiPythonImg --allow-missing-images --name apiimg


oc create route edge --service=api3scale --insecure-policy=Redirect
oc create route edge --service=apiimg --insecure-policy=Redirect


oc tag registry.access.redhat.com/ubi8/openjdk-8:1.14-14.1675788284  ubi8/openjdk-8:1.17-1.1693366248

https://access.redhat.com/documentation/en-us/openshift_container_platform/4.11/html/images/image-configuration


oc new-build --name apiPythonImg --binary --strategy docker

oc start-build --from-dir

oc new-app image-registry.openshift-image-registry.svc:5000/carlosxpk/img

oc create route edge --service=img --insecure-policy=Redirect
