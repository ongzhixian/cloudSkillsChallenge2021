# dotnet CLI

DESKTOP-NJM00MP>zhixian D:\src\github\cloudSkillsChallenge2021\RazorPagesPizza (main)
PS> dotnet new webapp

dotnet new page --name Pizza --namespace RazorPagesPizza.Pages --output Pages

----------------

DESKTOP-NJM00MP>zhixian D:\src\github\cloudSkillsChallenge2021\ContosoPizza (main)
PS> dotnet new webapi
The template "ASP.NET Core Web API" was created successfully

.NET HTTP Read-Eval-Print Loop (REPL) command-line tool (for making HTTP requests to our web API)
(Currently this tool seems to be available only for .NET 5?)

dotnet tool install -g Microsoft.dotnet-httprepl

Usage:
httprepl https://localhost:{PORT}

------------------

DESKTOP-NJM00MP>zhixian D:\src\github\cloudSkillsChallenge2021\BlazorApp (main)
PS> dotnet new blazorserver
The template "Blazor Server App" was created successfully

dotnet new razorcomponent -n Todo -o Pages

Razor component file names require a capitalized first letter. 
Open the Pages folder and confirm that the Todo component file name starts with a capital letter T. 
The file name should be Todo.razor.

----------------

PrintFramerAPI
http://localhost:5000/api/priceframe/6/17

dotnet add package Swashbuckle.AspNetCore

http://localhost:5000/swagger/v1/swagger.json


----------------

Microservices / Docker 101


DESKTOP-NJM00MP>zhixian D:\src\github\cloudSkillsChallenge2021\dotnetMicroServices\backend (main)
PS> docker build -t pizzabackend .

docker run -it --rm -p 5200:80 --name pizzabackendcontainer pizzabackend
http://localhost:5200/pizzainfo


build the container images:
`docker-compose build`

Start both the website and the web API,
`docker-compose up`

------------------

Kubernetes

docker-compose build
docker-compose up
http://localhost:5902

docker login
docker tag pizzafrontend zhixian/pizzafrontend
docker tag pizzabackend zhixian/pizzabackend

docker push zhixian/pizzafrontend
docker push zhixian/pizzabackend

(
    Requirement: Kubernetes cluster!
    Using the standalone Kubernetes server and client thats packaged with Docker Desktop.
    See: https://docs.docker.com/desktop/kubernetes/

)
kubectl config get-contexts
kubectl config use-context docker-desktop


kubectl apply -f backend-deploy.yml
kubectl apply -f frontend-deploy.yml
    tell Kubernetes to run the file we just created;
    kubectl apply command will return quickly, but the container creation may take a while

kubectl get pods
    View progress of containers being build.

PS> kubectl get pods
NAME                             READY   STATUS    RESTARTS   AGE
pizzabackend-587f9f56ff-rd8cv    1/1     Running   0          80s
pizzafrontend-68b9f89578-5jvz8   1/1     Running   0          60s


kubectl scale --replicas=5 deployment/pizzabackend
    scale up to 5 instances

PS> kubectl get pods
NAME                             READY   STATUS              RESTARTS   AGE
pizzabackend-587f9f56ff-256cn    0/1     ContainerCreating   0          5s
pizzabackend-587f9f56ff-hlx4q    0/1     ContainerCreating   0          5s
pizzabackend-587f9f56ff-j5w5q    0/1     ContainerCreating   0          5s
pizzabackend-587f9f56ff-rd8cv    1/1     Running             0          113s
pizzabackend-587f9f56ff-xktqb    0/1     ContainerCreating   0          5s
pizzafrontend-68b9f89578-5jvz8   1/1     Running             0          93s


kubectl scale --replicas=1 deployment/pizzabackend
    scale it down to 1 instance

PS> kubectl get pods
NAME                             READY   STATUS        RESTARTS   AGE
pizzabackend-587f9f56ff-256cn    0/1     Terminating   0          70s
pizzabackend-587f9f56ff-hlx4q    1/1     Terminating   0          70s
pizzabackend-587f9f56ff-j5w5q    0/1     Terminating   0          70s
pizzabackend-587f9f56ff-rd8cv    1/1     Running       0          2m58s
pizzabackend-587f9f56ff-xktqb    1/1     Terminating   0          70s
pizzafrontend-68b9f89578-5jvz8   1/1     Running       0          2m38s

PS> kubectl get pods
NAME                             READY   STATUS    RESTARTS   AGE
pizzabackend-587f9f56ff-rd8cv    1/1     Running   0          3m40s
pizzafrontend-68b9f89578-5jvz8   1/1     Running   0          3m20s


Kubernetes Resiliency

kubectl delete pod pizzafrontend-68b9f89578-5jvz8