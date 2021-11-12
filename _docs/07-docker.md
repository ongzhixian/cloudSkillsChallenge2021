# Docker

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY backend.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish -c release -o /app


Pull the mcr.microsoft.com/dotnet/sdk:6.0 image and name the image build.
Set the working directory within the image to /src.
Copy the file named backend.csproj found locally to the /src directory that was just created.
Calls dotnet restore on the project.
Copy everything in the local working directory to the image.
Calls dotnet publish on the project.


FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app
EXPOSE 80
EXPOSE 443
COPY --from=build /app .
ENTRYPOINT ["dotnet", "backend.dll"]



Pull the mcr.microsoft.com/dotnet/aspnet:6.0 image.
Set the working directory within the image to /app.
Exposes port 80 and 443.
Copy everything from the /app directory of the build image created above into the app directory of this image.
Sets the entrypoint of this image to dotnet and passes backend.dll as an argument.


DESKTOP-NJM00MP>zhixian D:\src\github\cloudSkillsChallenge2021\dotnetMicroServices\backend (main)
PS> docker build -t pizzabackend .

docker run -it --rm -p 5200:80 --name pizzabackendcontainer pizzabackend
http://localhost:5200/pizzainfo



```
version: '3.4'

services: 

  frontend:
    image: pizzafrontend
    build:
      context: frontend
      dockerfile: Dockerfile
    environment: 
      - backendUrl=http://backend
    ports:
      - "5902:80"
    depends_on: 
      - backend
  backend:
    image: pizzabackend
    build: 
      context: backend
      dockerfile: Dockerfile
    ports: 
      - "5900:80"
```


First it creates the frontend website, naming it pizza frontend. 
It tells Docker to build it, pointing to the Dockerfile found in the frontend folder. 
Then it sets an environment variable for the website: backendUrl=http://backend. 
Finally it opens a port and declares it depends on the backend service.

The backend service gets created next. 
It's named pizzabackend. 
It's built from the same Dockerfile you created in the previous exercise. 
The last command specifies which port to open.


build the container images:
`docker-compose build`

Start both the website and the web API,
`docker-compose up`

PS> docker-compose up
[+] Running 3/3
 - Network dotnetmicroservices_default       Created                                                                                          0.8s
 - Container dotnetmicroservices-backend-1   Created                                                                                          0.1s
 - Container dotnetmicroservices-frontend-1  Created                                                                                          0.1s
Attaching to dotnetmicroservices-backend-1, dotnetmicroservices-frontend-1

http://localhost:5902 
