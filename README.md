sudo apt install virtualbox

# check if bios VT or AMD-v activates

egrep --color 'vmx|svm' /proc/cpuinfo


# install minikibe
# levantar un cluster

curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \
  && chmod +x minikube

sudo cp minikube /usr/local/bin && rm minikube

# install kubectl
# command  para interecturar con Kubernetes (este donde este, en local o en el cloud)
# 

curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

# 

kubectl get nodes --> get nodes

# configuracion
~/.kube/config

(podemos usar kubectl o podemos usar otros como terraform aqui la configacion de la api de la configuracion)

Addons que podemos isntallar

minickube addons list 

minikube dashboard

minikube logs


# conceptos claves de kubernetes

un pod puede tener un contenedo o mas de uno pero es recomendable 1 pod por cada contenedor

se lanzan con mainifest



kubectl apply -f pod.yaml 


kubectl get pod webserver
kubectl describe pod webserver


kubectl exec -it webserver bash


kubectl delete pod webserver

minikube ssh # nos conectamos por ssh a la consola del master

kubectl port-forwarding webserver

