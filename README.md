https://strapi.io/
A content management system (CMS) is a computer software used to manage the creation and modification of digital content1. It is often abbreviated as CMS and helps users create, manage, and modify content on a website without the need for specialized technical knowledge2.
https://github.com/strapi/strapi

![alt text](image.png)

# 🚀 Strapi Docker and Kubernetes Deployment DevOps Challenge
  Let's explore 2 models. First a simple and fast deploy, wihth strapi and database at the same machine - Develop Done here 
   - To the future:
  Second one will deploy strapi to one server and a db mysql to another server separeted, though at same network - Production   
  
## ⚙️ Deployment Develop
Deploy Docker Develop ! DO NOT use "@" as part of your docker-hub password
[* Please reffer to the end of file to install all the tools]()
- Setting Your-Account/You-Repository/image-name:tag
 <br>

$User = "user"
 <br>

$Cred = "password"
 <br>

$DOCKER_IMAGE="jmuniz1985/app-dev:latest"
 <br>

docker login -u $User -p $Cred
 <br>

- Build and Test local image
 <br>

docker build -t $DOCKER_IMAGE .
 <br>

docker run -d -p 1337:1337 -t $DOCKER_IMAGE
 <br>

 -  Your browser http://127.0.0.1:1337/admin
 <br>

- upload image to docker hub docker hub if it's OK
 <br>

docker push $DOCKER_IMAGE
 <br>


 <br>

## 📚 Minikube Deploy for develop envirorment - 
[* Make your life easier by adding this line to your shell config:]()
 <br>

 - Linux
 <br>

set alias kube="minikube kubectl --"
 <br>

 - Windows
 <br>

alias kube="minikube kubectl --"
 <br>

 - Create a  deployment and expose it on port 80 :
minikube start
 <br>

kubectl create deployment app-dev --image=jmuniz1985/app-dev
 <br>

kubectl expose deployment app-dev --type=LoadBallancer --port=80
 <br>


###### #--type= 1 - Cluster IP: Accessible from within the Kubernetes cluster 2 - NodePort: Accessible from a Service outside the cluster, a Web browser or from another server 3 - LoadBalancer: Accessible from all other Networks eg. Internet 
 - kubectl port-forward service/app-dev 80:137
 <br>

minikube service app-dev
 <br>

<br>

## 🤫 Expose to Internet and Check everything
kubectl get services app-dev
 <br>

kubectl cluster-info dump
 <br>

kubectl get pod -A
 <br>

 - In another window, start the tunnel to create a routable IP for the ‘balanced’ deployment:
 <br>

nohup minikube tunnel &&
 - To get the Routable IP, run this command and examine the EXTERNAL-IP column:
 <br>

kubectl get services balanced
 <br>



 <br>


## 🚀 Deploy to gke low cost k8s (so expose to internet)

gcloud container clusters get-credentials sample-cluster --location=us-central1-f 
 <br>

gcloud desafio app clusters get-credentials
 <br>

#gcloud auth configure-docker
 <br>

gcloud auth configure-gke
 <br>

gcloud container clusters get-credentials desafio --zone us-central1-c --project strapi-384603
 <br>


kubectl apply -f /manifests/app-dev.yaml
 <br>

kubectl apply -f /manifests/app-dev-service.yaml
 <br>


<br>

# ✨ Check out app Web GUI and API

http://35.222.150.83/admin

$Auth-Bear =  "Waters"

curl -X GET "http://35.222.150.83:1337/api/cadastros"\
 -H "Content-Type: application/json" -H "accept: application/json" -H \
 "Authorization: Bearer "


<br><br>
# To be done
## ⚙️ Deployment Production (MySql )
$DOCKER_IMAGE = "jmuniz1985/app-db:latest"
docker-compose create
docker-compose build
docker-compose start
docker-compose start
docker-compose up -d
 - Kill  containers on this image before proceed# Capturing image id via scipt as a Variable is to improve this
docker images
docker tag Your-Image-ID $DOCKER_IMAGE
docker push $DOCKER_IMAGE
echo MYSQL_ROOT_PASSWORD=strapi

kubectl create deployment app-dev --image=jmuniz1985/app-db:latest
 <br>

kubectl port-forward service/app-dev 443:443
 <br>


 <br>


 <br>
<br>
<sub>
🤫 @!POSTMAN will only work with content-type on POST requests [Strapi is hiring](https://forum.strapi.io/t/post-url-is-not-working/18749/5) - I was sending data like this as in the tutorial but got the error (# error sending Body):  </sub>
{
    "title": "Test product",
    "description": "test product description.",
    "price": 99.99,
    "qty": 20
}
Solved the error with this.
 {
     "data": {
    "title": "Test product",
    "description": "test product description.",
    "price": 99.99,
    "qty": 20
    }
}

# Deploy das ferramentas no windows 11
# Install Chocolatey 
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))                                        
winget search Microsoft.PowerShell winget install --id Microsoft.Powershell --source winget winget install --id Microsoft.Powershell.Preview --source winget    
choco install nodejs-lts yarn minikube docker-desktop terraform gcloudsdk  -y

### Instal and configure WSL 
[Learn more](<br> 
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
wsl --set-default-version 2
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
wget https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
wsl_update_x64.msi
#[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
### Instal and configure compose if you receive a error
#Start-BitsTransfer -Source "https://github.com/docker/compose/releases/download/v2.17.2/docker-compose-Windows-x86_64.exe" -Destination $Env:ProgramFiles\Docker\docker-compose.exe)


documentation
gdk gke
https://cloud.google.com/sdk/gcloud/reference/container/clusters/get-credentials    
docker strapi
https://docs.strapi.io/dev-docs/installation/docker


