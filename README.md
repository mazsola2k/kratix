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

on the worker platform continue:

oc apply -f https://github.com/fluxcd/flux2/releases/latest/download/install.yaml
namespace/flux-system created
resourcequota/critical-pods created
customresourcedefinition.apiextensions.k8s.io/alerts.notification.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/buckets.source.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/gitrepositories.source.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/helmcharts.source.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/helmreleases.helm.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/helmrepositories.source.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/imagepolicies.image.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/imagerepositories.image.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/imageupdateautomations.image.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/kustomizations.kustomize.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/ocirepositories.source.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/providers.notification.toolkit.fluxcd.io created
customresourcedefinition.apiextensions.k8s.io/receivers.notification.toolkit.fluxcd.io created
serviceaccount/helm-controller created
serviceaccount/image-automation-controller created
serviceaccount/image-reflector-controller created
serviceaccount/kustomize-controller created
serviceaccount/notification-controller created
serviceaccount/source-controller created
clusterrole.rbac.authorization.k8s.io/crd-controller created
clusterrole.rbac.authorization.k8s.io/flux-edit created
clusterrole.rbac.authorization.k8s.io/flux-view created
clusterrolebinding.rbac.authorization.k8s.io/cluster-reconciler created
clusterrolebinding.rbac.authorization.k8s.io/crd-controller created
service/notification-controller created
service/source-controller created
service/webhook-receiver created
deployment.apps/helm-controller created
deployment.apps/image-automation-controller created
deployment.apps/image-reflector-controller created
deployment.apps/kustomize-controller created
deployment.apps/notification-controller created
deployment.apps/source-controller created
networkpolicy.networking.k8s.io/allow-egress created
networkpolicy.networking.k8s.io/allow-scraping created
networkpolicy.networking.k8s.io/allow-webhooks created

Pls check if helm is running:

oc get pods --namespace flux-system
NAME                                    READY   STATUS    RESTARTS   AGE
helm-controller-86d54c748d-92jxt        1/1     Running   0          5m53s
kustomize-controller-5cb99ff54f-wrmsl   1/1     Running   0          5m53s

Install git secrets on the worker:

oc apply -f worker-git-secret.yaml
secret/git-credentials created

Validate:

oc get secret git-credentials -n flux-system
NAME              TYPE                       DATA   AGE
git-credentials   kubernetes.io/basic-auth   2      2m35s

Install git repository on the worker:

 oc apply -f worker-gitrepository.yaml
gitrepository.source.toolkit.fluxcd.io/kratix-workload created

Validate:

oc -n flux-system get gitrepository kratix-workload -o yaml
apiVersion: source.toolkit.fluxcd.io/v1
kind: GitRepository
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"source.toolkit.fluxcd.io/v1","kind":"GitRepository","metadata":{"annotations":{},"name":"kratix-workload","namespace":"flux-system"},"spec":{"interval":"1m","ref":{"branch":"main"},"secretRef":{"name":"git-credentials","namespace":"flux-system"},"url":"https://github.com/mazsola2k/kratix.git"}}
  creationTimestamp: "2025-05-30T15:02:52Z"
  generation: 1
  name: kratix-workload
  namespace: flux-system
  resourceVersion: "205448"
  uid: 9e3f2df2-f300-4d15-aacb-55beaeb69bcd
spec:
  interval: 1m
  ref:
    branch: main
  secretRef:
    name: git-credentials
  timeout: 60s
  url: https://github.com/mazsola2k/kratix.git
status:
  observedGeneration: -1

As the observedGEneration: -1, need to Validate further:

oc -n flux-system get all
Warning: apps.openshift.io/v1 DeploymentConfig is deprecated in v4.14+, unavailable in v4.10000+
NAME                                        READY   STATUS    RESTARTS   AGE
pod/helm-controller-86d54c748d-4wtmk        1/1     Running   0          56s
pod/kustomize-controller-5cb99ff54f-lv8rm   1/1     Running   0          56s

NAME                              TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)   AGE
service/notification-controller   ClusterIP   172.30.70.210    <none>        80/TCP    57s
service/source-controller         ClusterIP   172.30.222.11    <none>        80/TCP    56s
service/webhook-receiver          ClusterIP   172.30.242.127   <none>        80/TCP    56s

NAME                                          READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/helm-controller               1/1     1            1           56s
deployment.apps/image-automation-controller   0/1     0            0           56s
deployment.apps/image-reflector-controller    0/1     0            0           56s
deployment.apps/kustomize-controller          1/1     1            1           56s
deployment.apps/notification-controller       0/1     0            0           56s
deployment.apps/source-controller             0/1     0            0           56s

NAME                                                    DESIRED   CURRENT   READY   AGE
replicaset.apps/helm-controller-86d54c748d              1         1         1       56s
replicaset.apps/image-automation-controller-66b4b689b   1         0         0       56s
replicaset.apps/image-reflector-controller-787bc48c9d   1         0         0       56s
replicaset.apps/kustomize-controller-5cb99ff54f         1         1         1       56s
replicaset.apps/notification-controller-6b679c6fcf      1         0         0       56s
replicaset.apps/source-controller-84bd99dd95            1         0         0       56s


Apply a patch for source-controller issues:

oc adm policy add-scc-to-user anyuid -z source-controller -n flux-system
oc adm policy add-scc-to-user anyuid -z image-automation-controller -n flux-system
oc adm policy add-scc-to-user anyuid -z image-reflector-controller -n flux-system
oc adm policy add-scc-to-user anyuid -z notification-controller -n flux-system

oc -n flux-system patch deployment source-controller --type=merge --patch '{
  "spec": {
    "template": {
      "metadata": {
        "annotations": {
          "container.seccomp.security.alpha.kubernetes.io/manager": null
        }
      },
      "spec": {
        "securityContext": {
          "fsGroup": null
        }
      }
    }
  }
}'


oc -n flux-system patch deployment image-automation-controller --type=merge -p='
spec:
  template:
    metadata:
      annotations:
        container.seccomp.security.alpha.kubernetes.io/manager: null
    spec:
      securityContext:
        fsGroup: null
'

oc -n flux-system patch deployment image-reflector-controller --type=merge -p='
spec:
  template:
    metadata:
      annotations:
        container.seccomp.security.alpha.kubernetes.io/manager: null
    spec:
      securityContext:
        fsGroup: null
'

oc -n flux-system patch deployment notification-controller --type=merge -p='
spec:
  template:
    metadata:
      annotations:
        container.seccomp.security.alpha.kubernetes.io/manager: null
    spec:
      securityContext:
        fsGroup: null
'
oc -n flux-system rollout restart deployment/source-controller
oc -n flux-system rollout restart deployment image-automation-controller
oc -n flux-system rollout restart deployment image-reflector-controller
oc -n flux-system rollout restart deployment notification-controller

Validate:

oc -n flux-system get all
Warning: apps.openshift.io/v1 DeploymentConfig is deprecated in v4.14+, unavailable in v4.10000+
NAME                                               READY   STATUS    RESTARTS   AGE
pod/helm-controller-86d54c748d-4wtmk               1/1     Running   0          33m
pod/image-automation-controller-57c64df47b-txpvw   1/1     Running   0          71s
pod/image-reflector-controller-76bd6fb789-cl2pz    1/1     Running   0          67s
pod/kustomize-controller-5cb99ff54f-lv8rm          1/1     Running   0          33m
pod/notification-controller-864b498bcc-v7djw       1/1     Running   0          66s
pod/source-controller-7d9c69c58f-hrxql             1/1     Running   0          10m

NAME                              TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)   AGE
service/notification-controller   ClusterIP   172.30.70.210    <none>        80/TCP    33m
service/source-controller         ClusterIP   172.30.222.11    <none>        80/TCP    33m
service/webhook-receiver          ClusterIP   172.30.242.127   <none>        80/TCP    33m

NAME                                          READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/helm-controller               1/1     1            1           33m
deployment.apps/image-automation-controller   1/1     1            1           33m
deployment.apps/image-reflector-controller    1/1     1            1           33m
deployment.apps/kustomize-controller          1/1     1            1           33m
deployment.apps/notification-controller       1/1     1            1           33m
deployment.apps/source-controller             1/1     1            1           33m

NAME                                                     DESIRED   CURRENT   READY   AGE
replicaset.apps/helm-controller-86d54c748d               1         1         1       33m
replicaset.apps/image-automation-controller-57c64df47b   1         1         1       71s
replicaset.apps/image-automation-controller-66b4b689b    0         0         0       33m
replicaset.apps/image-automation-controller-895946785    0         0         0       4m7s
replicaset.apps/image-reflector-controller-76bd6fb789    1         1         1       67s
replicaset.apps/image-reflector-controller-787bc48c9d    0         0         0       33m
replicaset.apps/image-reflector-controller-867cbb9d87    0         0         0       3m31s
replicaset.apps/kustomize-controller-5cb99ff54f          1         1         1       33m
replicaset.apps/notification-controller-6b679c6fcf       0         0         0       33m
replicaset.apps/notification-controller-864b498bcc       1         1         1       66s
replicaset.apps/notification-controller-f475469bd        0         0         0       3m15s
replicaset.apps/source-controller-59b79d76d9             0         0         0       11m
replicaset.apps/source-controller-7d9c69c58f             1         1         1       10m
replicaset.apps/source-controller-84bd99dd95             0         0         0       33m
replicaset.apps/source-controller-94c7f6b74              0         0         0       16m

You will need to re-add the  worker-gitrepository yaml and worker-git-secrey.yaml

After:

oc -n flux-system get gitrepository kratix-workload -o yaml
apiVersion: source.toolkit.fluxcd.io/v1
kind: GitRepository
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"source.toolkit.fluxcd.io/v1","kind":"GitRepository","metadata":{"annotations":{},"name":"kratix-workload","namespace":"flux-system"},"spec":{"interval":"1m","ref":{"branch":"main"},"secretRef":{"name":"git-credentials","namespace":"flux-system"},"url":"https://github.com/mazsola2k/kratix.git"}}
  creationTimestamp: "2025-05-30T15:57:30Z"
  finalizers:
  - finalizers.fluxcd.io
  generation: 1
  name: kratix-workload
  namespace: flux-system
  resourceVersion: "216528"
  uid: 2c6e20d2-ae88-4f62-80f3-aae40c5d7eab
spec:
  interval: 1m
  ref:
    branch: main
  secretRef:
    name: git-credentials
  timeout: 60s
  url: https://github.com/mazsola2k/kratix.git
status:
  artifact:
    digest: sha256:67c409bc3ff7a8f0bffffcafa3a89874edb66e192a79549a59e66cc4a764184f
    lastUpdateTime: "2025-05-30T15:57:33Z"
    path: gitrepository/flux-system/kratix-workload/9bd461d8e060fced248ec19403fd653ec8f8a5bf.tar.gz
    revision: main@sha1:9bd461d8e060fced248ec19403fd653ec8f8a5bf
    size: 4587
    url: http://source-controller.flux-system.svc.cluster.local./gitrepository/flux-system/kratix-workload/9bd461d8e060fced248ec19403fd653ec8f8a5bf.tar.gz
  conditions:
  - lastTransitionTime: "2025-05-30T15:57:33Z"
    message: stored artifact for revision 'main@sha1:9bd461d8e060fced248ec19403fd653ec8f8a5bf'
    observedGeneration: 1
    reason: Succeeded
    status: "True"
    type: Ready
  - lastTransitionTime: "2025-05-30T15:57:33Z"
    message: stored artifact for revision 'main@sha1:9bd461d8e060fced248ec19403fd653ec8f8a5bf'
    observedGeneration: 1
    reason: Succeeded
    status: "True"
    type: ArtifactInStorage
  observedGeneration: 1

To reconcile without the flux CLI - Patch:
oc -n flux-system patch kustomization kratix-workload --type=merge -p '{"spec":{"force":true}}'

Howto Test - Push changes to git:
oc -n flux-system annotate kustomization/kratix-workload fluxcd.io/reconcileAt="$(date -u +%Y-%m-%dT%H:%M:%SZ)"
kustomization.kustomize.toolkit.fluxcd.io/kratix-workload annotate

Install a sample prmoise - Jenkins - issue from the kratix-platform:
export KRATIX_MARKETPLACE_REPO="https://raw.githubusercontent.com/syntasso/kratix-marketplace/main" 

oc apply  --filename "${KRATIX_MARKETPLACE_REPO}/jenkins/promise.yaml"
promise.platform.kratix.io/jenkins created

oc get crds jenkins.marketplace.kratix.io
NAME                            CREATED AT
jenkins.marketplace.kratix.io   2025-05-30T16:46:54Z

Validate
oc get pods --watch
NAME                               READY   STATUS    RESTARTS      AGE
jenkins-operator-b975597c8-tx68f   1/1     Running   6 (58s ago)   99m

Request a resource through the kratix platform:
oc apply --filename "${KRATIX_MARKETPLACE_REPO}/jenkins/resource-request.yaml"
jenkins.marketplace.kratix.io/example created

oc get jenkins.marketplace.kratix.io
NAME      STATUS
example   Resource requested

It takes some time for the kratix dev example resource to be up from creating state to running:

oc get pods --watch
NAME                               READY   STATUS    RESTARTS        AGE
jenkins-operator-b975597c8-tx68f   1/1     Running   6 (3m44s ago)   101m
 ^Hjenkins-dev-example                0/1     Pending   0               0s
jenkins-dev-example                0/1     Pending   0               0s
jenkins-dev-example                0/1     Pending   0               0s
jenkins-dev-example                0/1     ContainerCreating   0               0s
jenkins-dev-example                0/1     ContainerCreating   0               0s
jenkins-dev-example                0/1     ContainerCreating   0               6s
jenkins-dev-example                0/1     Running             0               74s
jenkins-dev-example                1/1     Running             0               2m41s

Run the below command - preferable from Windows Desktop or Linux Desktop with GUI - because you opening a connection between your openshift client and server directly:
oc port-forward jenkins-dev-example 8080:8080
Forwarding from 127.0.0.1:8080 -> 8080
Forwarding from [::1]:8080 -> 8080
Handling connection for 8080
Handling connection for 8080

You can get the actual jenkins username and password for the login with the below commands:
oc get secret jenkins-operator-credentials-dev-example  -o 'jsonpath={.data.user}' | base64 -d
oc get secret jenkins-operator-credentials-dev-example  -o 'jsonpath={.data.password}' | base64 -d  
