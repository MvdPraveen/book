
### BookShop App Architecture Steps
----------------------------------
-------------------------------------
![Architecture](Image1.png)
1. Create a Vnet1 and subnet1 with bookshopapprg1

vnet ip address range - 10.50.0.0/16
subnet1 - 10.50.1.0/24

2. Create second vnet and subnet with bookshopapprg1

vnet ip address range - 10.90.0.0/16
subnet2 -  10.90.1.0/24
## 1. Download .net sdk SDK 6.0.306
https://dotnet.microsoft.com/en-us/download/dotnet/6.0
2. Install .net sdk
3. Verify the dotnet version

## Intsall extensions in VS code
-----------------------
1. Install C# extension, Azure Account, App service

## Catalog Service Setup
-----------------------------------
## Setup up catalog service - local desktop

1. Copy the catalog code base into local system
2. open the code with VSCode
3. build the project
   $ dotnet build 
4. publish the project
   $ dotnet publish -o publish
   it will create a folder called publish

5.  code location
https://github.com/demoorg-practice/DevOps-Cloud-Architecure.git
Catalog Branch

## Setup up catalog service - Windows Server
6. Install IIS
7. Install dotnet core 6
https://dotnet.microsoft.com/en-us/download/dotnet/6.0

8. Copy publish folder to server C drive
9. Create a website and map to local path

## Weather service setup

1. create a ubuntu20.4 server
2. install git onther weather server - 
   $ sudo apt install git
3. Download the code using command 
   $ git clone https://github.com/demoorg-practice/DevOps-Cloud-Architecure.git
4. Execute commands
   $ sudo apt update
   $ sudo apt install nodejs
   $ sudo apt install npm
   $ sudo npm start

## Inventory service setup   

## Setup up Inventory service - local desktop

1. Copy the Inventory code base into local system
https://github.com/demoorg-practice/DevOps-Cloud-Architecure.git
2. open the code with VSCode
3. build the project
   $ dotnet build 
4. publish the project
   $ dotnet publish -o publish
   it will create a folder called publish
5. Go to publish folder right click -> Deploy to webapp   

## SetUp Cart service using docker, Azure Container registry and Kubernetes
1. Setup Docker server with ubuntu OS
https://docs.docker.com/engine/install/ubuntu/
2. Install git in the docker server
3. Create git PAT token and Clone the Cart code to docker server
Git clone https://github.com/demoorg-practice/DevOps-Cloud-Architecure.git
4. Open the folder & Create docker image using docker build command
5. Create Azure Container regisrty
https://learn.microsoft.com/en-us/azure/container-registry/container-registry-get-started-portal?tabs=azure-cli
6. Install azure CLI in the docker server to Push the image from docker server to container registry
https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt
7. Now login to Azure container regstry from docker server using Azure Cli
8. Use az login command to login azure cloud
9. $ docker login azurecr.io -u username -p COPIEDKEYAZURECONTAINERREGISTRY

10. Add the docker image tag before pushing to Azure Container registry
    $ docker tag imagename acrregistryname/imagename
11. Now Push the docker the image from docker server to Azure Container Registry 
   $ docker push bookshopacr101.azurecr.io/cart:latest   
12. Now observe the pushed image in the Azure Container Regisrty
13. Create kubernetes cluster with Azure Container registry
https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal?tabs=azure-cli
14. Add kubernetes plugin in visual studio code 
15. Login to Kubernetes cluster using Azure CLI
    $ az aks get-credentials -n bookshopkube101 -g bookshopaaprg1
16. update Azure container regisrty name in Kubernetes deployment.yml file
17. Depoly application into the kubernetes cluster
18. Verify the app with service IP address











