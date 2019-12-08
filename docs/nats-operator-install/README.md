# NATS operator install

.yaml files copied from https://github.com/nats-io/nats-operator/tree/master/deploy

namespace `nats-io` replaced where indicated by the comments + feature flag uncommented for cluster scoped

## Install:

Create a `nats-io`  namespace:

```
kubectl create ns nats-io
```

Install the NATS operator on your K8s cluster:

```
kubectl apply -f 00-prereqs.yaml
kubectl apply -f 10-deployment.yaml
```

Ensure you have the CRDs installed:

```
NAME                       CREATED AT
natsclusters.nats.io       2019-12-08T15:03:48Z
natsserviceroles.nats.io   2019-12-08T15:03:48Z
```

Then create your cluster

```
kubectl apply -f example-nats-cluster-crd.yaml
NAME                     READY   STATUS    RESTARTS   AGE
example-nats-cluster-1   1/1     Running   0          15s
example-nats-cluster-2   1/1     Running   0          13s
example-nats-cluster-3   1/1     Running   0          12s
```
