## AZ-204 Azure container

`Azure Container Instance`, which is the fastest way and simplest way to run a container in Azure 

PreRequest
Installations:
 1. Docker desktop for more details https://docs.docker.com/get-docker/
 2. Docker extension in VisualStudio Code
 3. Import the App containing Dockerfile
 4. Create Azure container registry (ACR)

Go to VS Code -> Docker panel to see container registers, images and containers. 
 COnnect to Azure Container Register
 1. Build the docker image if not otherwise select image to push in to the ACR 
 2. Deploy the image in ACR to Azure container instance either by going to the Azure portal or from 
   VS Code Docker extension.
 3. Go to VS Code -> Docker panel  -> AZ Container Register -> Select image -> Deploy Image to Azure Container Instances.
 4. Go to Azure -> container instance -> check Container status (Running) -> logs
 5. Connect with container public IP Address  (e.g)
 ` curl -X POST -H "Content-Type:application/json" -d '{ "name" : "Buy milk", "completed" : false } http://20.72.139.128:8080/todos`
