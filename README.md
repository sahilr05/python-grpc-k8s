## Requirements:
* minikube
* python3.6+
* docker

## How to run it locally
```
git clone https://github.com/sahilr05/python-grpc-k8s.git
cd python-grpc-k8s
minikube start
eval $(minikube docker-env)         
docker build -f Dockerfile.server -t grpc_server .
kubectl apply -f kubernetes/
python python-grpc-k8s/client.py --server-ip $(minikube ip)
```
