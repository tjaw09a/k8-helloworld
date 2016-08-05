# k8-helloworld
Simple hello world webservice (node.js app) running in Kubernetes 

To run this locally, install and run Minikube: http://kubernetes.io/docs/getting-started-guides/minikube/

Set up Docker client to use Docker daemon running in Minikube VM:
```
eval $(minikube docker-env)
```

Build the Docker image: 
```
docker build -t nodehello:v1 .
```

Create the hello world service:
```
kubectl create -f hello-node-service.yaml
```

Find IP for webservice:
```
minikube ip
```

Find port (NodePort) for webservice:
```
kubectl describe services hello-node
```

Use browser or other http client to hit url (http://ip:port) to see "Hello World"

