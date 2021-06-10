# GRPC implementaion using python and k8s <br>
## Requirements:
* minikube
* python3.6+
* docker

## How to run it locally
* Clone this repo
```
git clone https://github.com/sahilr05/python-grpc-k8s.git
```
* Switch to project directory
```
cd python-grpc-k8s
```
* Start minikube
```
minikube start
```
* Point your terminal to use the docker daemon inside minikube
```
eval $(minikube docker-env)        
```
* Build docker image
```
docker build -f Dockerfile.server -t grpc_server .
```
* Apply changes
```
kubectl apply -f kubernetes/
```
* Execute client side code
```
python python-grpc-k8s/client.py --server-ip $(minikube ip)
```

## References
* [GRPC Python](https://grpc.io/docs/languages/python/)
* [CLevasseur/grpc-kubernetes](https://github.com/CLevasseur/grpc-kubernetes)
