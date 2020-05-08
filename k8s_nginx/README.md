# Kubernetes for Nginx

## Introduction

Running a Nginx app with 3 replicas. And expose service with high port.

## Detail

Kubernetes can be set up by imperative (CLI) / declarative (spec file) ways.

## Usage

### Imperative way (CLI)

```bash
// create deployment, pod
kubectl create deployment my-nginx --image nginx

// scale from 1 pod to 3 pods
kubectl scale deployment.apps/my-nginx --replicas=3

// expose deployment, pod (create a NodePort service)
kubectl expose deployment my-nginx --port=80 --type=NodePort --name=my-nginx-service

// query port mapping
kubectl describe service -l app=my-nginx

// tear down
kubectl delete deployment my-nginx &&
kubectl delete service my-nginx-service
```

### Declarative way (spec file)

```bash
// create service, deployment, pods
kubectl apply -f nginx-app.yml

// tear down
kubectl delete -f nginx-app.yml
```

## Tips

* Using  `kubectl get ${resource} -w` to monitor a real time change log.
* Command validation:
  * Adding `--dry-run` into imperative commands for client side validation.
  * Adding `--server-dry-run` into imperative commands for server side validation.
* Adding `-o yaml` into imperative commands can display the YAML spec.
