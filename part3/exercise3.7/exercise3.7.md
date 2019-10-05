# exercise 3.7, b

Docker is a platform. With Docker you can put apps in containers and run apps that are in containers. The basic idea with Docker is to keep the environments and components that app needs in the same place. That way it is possible to run the app lighter on the server than without containers. With Docker apps are also easy to move from one computer to another because the whole app and its components are in one place. Containers can also be used in CI/CD (continuous integration/continuous deployment): code can be deployed efficiently. Containers are also easy to deploy in cloud.

VMs are more heavier than Docker because they emulate virtual hardware. One could say that Docker is a lighter version of VMs because it uses shared operating systems. In a picture below is also described how VMs differ from containers:
![Containers vs VMs](docker.png)

One example with Docker containers:
Our exercise frontend project, simple version:

Dockerfile:
```
FROM ubuntu:16.04 

ENV API_URL=http://localhost:8000

RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    apt-get purge -y --auto-remove curl && \
    rm -rf /var/lib/apt/lists/* 
WORKDIR /app
COPY . .
RUN npm install

EXPOSE 5000

CMD ["npm", "start"]
```

The code above will install nodejs into a container/image and it is possible that this app can be run on a computer where nodejs is not installed: Less space is taken but still it is possible to deploy the frontend project on a computer where nodejs is not installed.

