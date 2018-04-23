#Launch Single Node Kubernetes Cluster
```
minikube version
minikube start
```
#Show cluster status
```
kubectl cluster-info
```

#Show json dump
```
kubectl cluster-info dump
```

#Starting deployment
```
kubectl run first-deployment --image=katacoda/docker-http-server --port=80
```
```
kubectl get pods
```

#Exposing container via different networking options
```
kubectl expose deployment first-deployment --port=80 --type=NodePort
```
#List all services running
```
kubectl get svc 
```
#Starting curl
```
export PORT=$(kubectl get svc first-deployment -o go-template='{{range.spec.ports}}{{if .nodePort}}{{.nodePort}}{{"\n"}}{{end}}{{end}}')
echo "Accessing host01:$PORT"
curl host01:$PORT
```
