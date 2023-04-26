# 🚀 Deploy Model One - First a simple as fast deploy, then a production one where eu construct a db mysql machine/container separeted, though at same network ...*- Please reffer to the end of file to install all the tools
# 

# Deploy DOCKER Develop # DO NOT use "@" as part of your docker-hub password
$User = "user"
$Cred = "password"
docker login -u $User -p $Cred
# Setting Your-Account/You-Repository/image-name:tag
$DOCKER_IMAGE="jmuniz1985/app-dev:latest"
docker build -t $DOCKER_IMAGE .
#  Test local image. Exit terminal if you won't create anything by the time, just want you container running on the internet
docker run -p 1337:1337 -t $DOCKER_IMAGE
# upload image to dcr.io/$DOCKER_IMAGE
docker push $DOCKER_IMAGE
 
<br>
## 📚 Minikube Deploy for develop envirorment - Make your life easier by adding this line to your shell config:
# Linux
set alias kube="minikube kubectl --"
# Windows
alias kube="minikube kubectl --"
minikube start
# Create a  deployment and expose it on port 443:
kubectl create deployment app-dev --image=jmuniz1985/app-dev:latest
# use kubectl to forward the port:
kubectl expose deployment app-dev --type=NodePort --port=80
# Test local in your browser:
kubectl port-forward service/app-dev 80:80
minikube service app-dev

# Create a  deployment and expose it on port 443:
kubectl create deployment app-prod --image=jmuniz1985/app-prod:latest
kubectl expose deployment app-prod --type=NodePort --port=443
# use kubectl to forward the port:
kubectl port-forward service/app-prod 443:443
minikube service app-prod

# Check everything
kubectl get services app-dev
kubectl get services app-prod
kubectl cluster-info dump
kubectl get pod -A
kubectl -- get pod -A

# In another window, start the tunnel to create a routable IP for the ‘balanced’ deployment:
nohup minikube tunnel &&
# Routable IP run this command and examine the EXTERNAL-IP column:
kubectl get services balanced

# Checkk the app Web GUI
http://127.0.0.1:1337/admin
# test API
curl -X GET "http://34.133.130.242:1337/api/cadastros"\
 -H "Content-Type: application/json" -H "accept: application/json" -H \
 "Authorization: Bearer 92ea49a61ffca76eedbf50e90052b6d43bec3fa27bafedfd5f2f38e7b7af7c9646bdef4f3b6820eea008cec861a4c0d29b5e7f3bacaf34e37ec176913fa8df061c927e530dc2eb8d0ce449fd15ccd900334c65ccdd1806e731bfc16e0eecff44c7ca771b39ba6a9498be150a4ad369dc38ca6e43ca2895860bde39c665e83290"
<br>







$DOCKER_IMAGE = "jmuniz1985/app-db:latest"

docker login -u $User -p $Cred
docker-compose create
docker-compose build
docker-compose start
docker-compose start
docker-compose up -d
# Kill any containers on this image before proceed from here!

docker images
# Mellhorar capturando imageid via scipt e carregando como variável
docker tag 68cab8b895fc $DOCKER_IMAGE
docker push $DOCKER_IMAGE






docker push 
docker tag dd6675b5cfea  
 



### LoadBalancer is a convenient way to expose a Service to the internet 
[Learn more](<br> 
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
wsl --set-default-version 2
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
wget https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
wsl_update_x64.msi
#[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
#Start-BitsTransfer -Source "https://github.com/docker/compose/releases/download/v2.17.2/docker-compose-Windows-x86_64.exe" -Destination $Env:ProgramFiles\Docker\docker-compose.exe)

```
npm run start
# or
yarn start
```

### `build`

Build your admin panel. [Learn more](https://docs.strapi.io/developer-docs/latest/developer-resources/cli/CLI.html#strapi-build)

```
npm run build
# or
yarn build
```

## ⚙️ Deployment

Strapi gives you many possible deployment options for your project. Find the one that suits you on the [deployment section of the documentation](https://docs.strapi.io/developer-docs/latest/setup-deployment-guides/deployment.html).



- [Resource center](https://strapi.io/resource-center) - Strapi resource center.
- [Strapi documentation](https://docs.strapi.io) - Official Strapi documentation.
- [Strapi tutorials](https://strapi.io/tutorials) - List of tutorials made by the core team and the community.
- [Strapi blog](https://docs.strapi.io) - Official Strapi blog containing articles made by the Strapi team and the community.
- [Changelog](https://strapi.io/changelog) - Find out about the Strapi product updates, new features and general improvements.

Feel free to check out the [Strapi GitHub repository](https://github.com/strapi/strapi). Your feedback and contributions are welcome!

## ✨ Community

- [Discord](https://discord.strapi.io) - Come chat with the Strapi community including the core team.
- [Forum](https://forum.strapi.io/) - Place to discuss, ask questions and find answers, show your Strapi project and get feedback or just talk with other Community members.
- [Awesome Strapi](https://github.com/strapi/awesome-strapi) - A curated list of awesome things related to Strapi.





# Deploy das ferramentas no windows 11
# Install Chocolatey 
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))                                        
winget search Microsoft.PowerShell winget install --id Microsoft.Powershell --source winget winget install --id Microsoft.Powershell.Preview --source winget    
choco install nodejs-lts yarn minikube docker-desktop terraform gcloudsdk  -y

<sub>🤫 @!POSTMAN will only work with content-type on POST requests [Strapi is hiring](https://forum.strapi.io/t/post-url-is-not-working/18749/5) - I was sending data like this as in the tutorial but got the error (# error sending Body):  </sub>
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

