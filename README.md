sudo apt-get update -y  
sudo apt-get upgrade -y  
sudo apt-get install curl  
sudo apt-get install apt-transport-https  
sudo apt install virtualbox virtualbox-ext-pack  
wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64  
sudo cp minikube-linux-amd64 /usr/local/bin/minikube  
sudo chmod 755 /usr/local/bin/minikube  
minikube version  
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl  
chmod +x ./kubectl  
sudo mv ./kubectl /usr/local/bin/kubectl  
kubectl version -o json  
minikube start  
minikube addons enable ingress  
mkdir k8s  
cd myapp  
ll  
eval $(minikube docker-env)  
docker build -t nodeapp .  
cd ..  
cd k8s  
vi nodeapp-deployment.yml  
kubectl apply -f nodeapp-deployment.yml  
kubectl delete deploy nodeapp-deployment  
vi nodeapp-deployment-svc.yml  
kubectl apply -f nodeapp-deployment-svc.yml  
vi nodeapp-ingress.yml  
vi nodeapp-deployment-svc.yml  
vi /etc/hosts  
kubectl delete svc nodeapp-service  
kubectl delete deploy nodeapp-deployment  
kubectl apply -f nodeapp-deployment-svc.yml  
kubectl apply -f nodeapp-ingress.yml  
curl -kL http://host.info/  
