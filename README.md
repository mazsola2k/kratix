# kratix
Kratix Platform Engineering Framework related deployment information

oc apply --filename https://github.com/cert-manager/cert-manager/releases/download/v1.15.0/cert-manager.yaml
namespace/cert-manager created
customresourcedefinition.apiextensions.k8s.io/certificaterequests.cert-manager.io created
customresourcedefinition.apiextensions.k8s.io/certificates.cert-manager.io created
customresourcedefinition.apiextensions.k8s.io/challenges.acme.cert-manager.io created
customresourcedefinition.apiextensions.k8s.io/clusterissuers.cert-manager.io created
customresourcedefinition.apiextensions.k8s.io/issuers.cert-manager.io created
customresourcedefinition.apiextensions.k8s.io/orders.acme.cert-manager.io created
serviceaccount/cert-manager-cainjector created
serviceaccount/cert-manager created
serviceaccount/cert-manager-webhook created
clusterrole.rbac.authorization.k8s.io/cert-manager-cainjector created
clusterrole.rbac.authorization.k8s.io/cert-manager-controller-issuers created
clusterrole.rbac.authorization.k8s.io/cert-manager-controller-clusterissuers created
clusterrole.rbac.authorization.k8s.io/cert-manager-controller-certificates created
clusterrole.rbac.authorization.k8s.io/cert-manager-controller-orders created
clusterrole.rbac.authorization.k8s.io/cert-manager-controller-challenges created
clusterrole.rbac.authorization.k8s.io/cert-manager-controller-ingress-shim created
clusterrole.rbac.authorization.k8s.io/cert-manager-cluster-view created
clusterrole.rbac.authorization.k8s.io/cert-manager-view created
clusterrole.rbac.authorization.k8s.io/cert-manager-edit created
clusterrole.rbac.authorization.k8s.io/cert-manager-controller-approve:cert-manager-io created
clusterrole.rbac.authorization.k8s.io/cert-manager-controller-certificatesigningrequests created
clusterrole.rbac.authorization.k8s.io/cert-manager-webhook:subjectaccessreviews created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-cainjector created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-controller-issuers created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-controller-clusterissuers created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-controller-certificates created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-controller-orders created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-controller-challenges created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-controller-ingress-shim created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-controller-approve:cert-manager-io created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-controller-certificatesigningrequests created
clusterrolebinding.rbac.authorization.k8s.io/cert-manager-webhook:subjectaccessreviews created
role.rbac.authorization.k8s.io/cert-manager-cainjector:leaderelection created
role.rbac.authorization.k8s.io/cert-manager:leaderelection created
role.rbac.authorization.k8s.io/cert-manager-webhook:dynamic-serving created
rolebinding.rbac.authorization.k8s.io/cert-manager-cainjector:leaderelection created
rolebinding.rbac.authorization.k8s.io/cert-manager:leaderelection created
rolebinding.rbac.authorization.k8s.io/cert-manager-webhook:dynamic-serving created
service/cert-manager created
service/cert-manager-webhook created
deployment.apps/cert-manager-cainjector created
deployment.apps/cert-manager created
deployment.apps/cert-manager-webhook created
mutatingwebhookconfiguration.admissionregistration.k8s.io/cert-manager-webhook created
validatingwebhookconfiguration.admissionregistration.k8s.io/cert-manager-webhook created

oc get pods -n cert-manager
NAME                                       READY   STATUS    RESTARTS   AGE
cert-manager-86d8bf849b-78whj              1/1     Running   0          3m39s
cert-manager-cainjector-66886db7db-zjtc8   1/1     Running   0          3m39s
cert-manager-webhook-86775f7cf6-xbblw      1/1     Running   0          3m39s

oc apply --filename https://github.com/syntasso/kratix/releases/latest/download/kratix.yaml                                      
namespace/kratix-platform-system created
customresourcedefinition.apiextensions.k8s.io/bucketstatestores.platform.kratix.io created
customresourcedefinition.apiextensions.k8s.io/destinations.platform.kratix.io created
customresourcedefinition.apiextensions.k8s.io/gitstatestores.platform.kratix.io created
customresourcedefinition.apiextensions.k8s.io/healthrecords.platform.kratix.io created
customresourcedefinition.apiextensions.k8s.io/promisereleases.platform.kratix.io created
customresourcedefinition.apiextensions.k8s.io/promises.platform.kratix.io created
customresourcedefinition.apiextensions.k8s.io/workplacements.platform.kratix.io created
customresourcedefinition.apiextensions.k8s.io/works.platform.kratix.io created
serviceaccount/kratix-platform-controller-manager created
role.rbac.authorization.k8s.io/kratix-platform-leader-election-role created
clusterrole.rbac.authorization.k8s.io/kratix-platform-manager-role created
clusterrole.rbac.authorization.k8s.io/kratix-platform-metrics-auth-role created
clusterrole.rbac.authorization.k8s.io/kratix-platform-metrics-reader created
rolebinding.rbac.authorization.k8s.io/kratix-platform-leader-election-rolebinding created
clusterrolebinding.rbac.authorization.k8s.io/kratix-platform-manager-rolebinding created
clusterrolebinding.rbac.authorization.k8s.io/kratix-platform-metrics-auth-rolebinding created
configmap/kratix-platform-pipeline-adapter-config created
service/kratix-platform-controller-manager-metrics-service created
service/kratix-platform-webhook-service created
deployment.apps/kratix-platform-controller-manager created
certificate.cert-manager.io/kratix-platform-metrics-server-cert created
certificate.cert-manager.io/kratix-platform-serving-cert created
issuer.cert-manager.io/kratix-platform-selfsigned-issuer created
mutatingwebhookconfiguration.admissionregistration.k8s.io/kratix-platform-mutating-webhook-configuration created
validatingwebhookconfiguration.admissionregistration.k8s.io/kratix-platform-validating-webhook-configuration create

In case Kratix installed properly:

oc get pods --namespace kratix-platform-system
NAME                                                  READY   STATUS    RESTARTS   AGE
kratix-platform-controller-manager-8576fdbc85-44rks   1/1     Running   0          25s

In case Kratix Container Image not pulled:

oc get pods --namespace kratix-platform-system
NAME                                                READY   STATUS             RESTARTS   AGE
kratix-platform-controller-manager-88994d65-25zz5   0/1     ImagePullBackOff   0          6m33s

oc get pod kratix-platform-controller-manager-88994d65-25zz5 -n kratix-platform-system -o jsonpath='{.spec.containers[*].image}'
syntasso.docker.scarf.sh/syntasso/kratix-platform@sha256:6499bf5961e0670fe823e16cd106a2ada5d8fb1d2f4e2c3924e6d33ad318096e[mazsola@localhost auth]$ 

!!!!!!!
!!!!The image pull is failing due to the use of syntasso.docker.scarf.sh, which does not always resolve or behave correctly in OpenShift clusters.
!!!!!!!!

ssh core@openshift-platform@modernhackers.com
podman pull docker.io/syntasso/kratix-platform@sha256:6499bf5961e0670fe823e16cd106a2ada5d8fb1d2f4e2c3924e6d33ad318096e
Trying to pull docker.io/syntasso/kratix-platform@sha256:6499bf5961e0670fe823e16cd106a2ada5d8fb1d2f4e2c3924e6d33ad318096e...
Getting image source signatures
Copying blob 35d697fe2738 done   | 
Copying blob 4eff9a62d888 done   | 
Copying blob bfb59b82a9b6 done   | 
Copying blob 7c12895b777b done   | 
Copying blob a62778643d56 done   | 
Copying blob 3214acf345c0 done   | 
Copying blob 5664b15f108b done   | 
Copying blob 0bab15eea81d done   | 
Copying blob 4aa0ea1413d3 done   | 
Copying blob da7816fa955e done   | 
Copying blob 9aee425378d2 done   | 
Copying blob d00c3209d929 done   | 
Copying blob c1e595f74d52 done   | 
Copying blob 7faf0cfa885c done   | 
Copying blob 5b14f6c9a813 done   | 
Copying blob 33ce0b1d99fc done   | 
Copying blob f45e0372ce60 done   | 
Copying blob c37c50f5c5cd done   | 
Copying blob e838806f649a done   | 
Copying config 3863cfc5e6 done   | 
Writing manifest to image destination

oc patch deployment kratix-platform-controller-manager \
  -n kratix-platform-system \
  --type='json' \
  -p='[{"op": "replace", "path": "/spec/template/spec/containers/0/image", "value": "docker.io/syntasso/kratix-platform@sha256:6499bf5961e0670fe823e16cd106a2ada5d8fb1d2f4e2c3924e6d33ad318096e"}]'

deployment.apps/kratix-platform-controller-manager patched

oc get pods -n kratix-platform-system
NAME                                                  READY   STATUS    RESTARTS   AGE
kratix-platform-controller-manager-7777b59d97-dzkdw   1/1     Running   0          13s

You will need two openshift clusters - independent ones. 
1 platform  - we call openshift.modernhackers.com
1 worker - we call openshift-worker.modernhackers.com

Apply the following services on the platform openshift:

oc apply -f git-secret.yaml
secret/git-credentials created

validate:
oc get secret git-credentials -n kratix-platform-system
NAME              TYPE                       DATA   AGE
git-credentials   kubernetes.io/basic-auth   2      3m39s

oc apply -f git-state-store.yaml
gitstatestore.platform.kratix.io/my-git-store created


validate:

oc describe gitstatestore my-git-store -n kratix-platform-system
Name:         my-git-store
Namespace:    
Labels:       <none>
Annotations:  <none>
API Version:  platform.kratix.io/v1alpha1
Kind:         GitStateStore
Metadata:
  Creation Timestamp:  2025-05-25T14:25:02Z
  Generation:          1
  Resource Version:    25771
  UID:                 851aaef8-589e-4323-b256-e7e5950bd7bc
Spec:
  Auth Method:  basicAuth
  Branch:       main
  Git Author:
    Name:  kratix
  Secret Ref:
    Name:  git-credentials
  URL:     https://github.com/mazsola2k/kratix.git
Status:
  Conditions:
    Last Transition Time:  2025-05-25T14:25:02Z
    Message:               Error initialising writer: secret "git-credentials" not found in namespace "default"
    Reason:                ErrorInitialisingWriter
    Status:                False
    Type:                  Ready
  Status:                  NotReady
Events:
  Type     Reason    Age    From                     Message
  ----     ------    ----   ----                     -------
  Warning  NotReady  4m14s  GitStateStoreController  GitStateStore "my-git-store" is not ready: Error initialising writer: secret "git-credentials" not found in namespace "default"


oc apply -f destination.yaml
destination.platform.kratix.io/openshift-worker created

oc describe Destination openshift-worker -n kratix-platform-system                            
Name:         openshift-worker
Namespace:    
Labels:       environment=dev
Annotations:  <none>
API Version:  platform.kratix.io/v1alpha1
Kind:         Destination
Metadata:
  Creation Timestamp:  2025-05-29T21:42:21Z
  Generation:          1
  Resource Version:    245534
  UID:                 821214b3-7adf-41d8-b7e6-fa9c868671ca
Spec:
  Cleanup:  none
  Filepath:
    Mode:  nestedByMetadata
  Init Workloads:
    Enabled:  true
  Path:       openshift-worker
  State Store Ref:
    Kind:  GitStateStore
    Name:  my-git-store
Status:
  Conditions:
    Last Transition Time:  2025-05-29T21:42:29Z
    Message:               Test documents written to State Store
    Reason:                TestDocumentsWritten
    Status:                True
    Type:                  Ready
Events:
  Type    Reason            Age   From                   Message
  ----    ------            ----  ----                   -------
Normal  DestinationReady  57s   DestinationController  Destination "openshift-worker" is ready
