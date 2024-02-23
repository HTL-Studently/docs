# Containerization

# Docker Secrets

To ensure a secure container environment Docker Secrets are used for any data that shouldn’t be transmitted or stored unencrypted.  
Docker Compose provides a way to use secrets without having to use environment variables to store information. If passwords and API keys are injected as environment variables, there is a risk of unintentional information exposure. Environment variables are often available to all processes, and it can be difficult to track access. They can also be printed in logs when debugging errors. Using secrets mitigates these risks.

After docker swarm is initialized, the secrets are added by using following command:
```
Echo “<password>” | sudo docker secret create NAME_OF_SECRET
```

After this the “NAME_OF_SECRET” is used in the files replacing hardcoded passwords or API keys.

# Dockerfile

Set environment variables to suppress interactive installation
```
ENV DEBIAN_FRONTEND=noninteractive
```

Install dependencies
```
RUN apt-get update
RUN apt-get install -y curl 
RUN apt-get install git 
```

Install NVM (Node Version Manager)
```
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

Load NVM and install the latest version of Node.js
```
RUN export NVM_DIR="$HOME/.nvm" && \
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" && \
    nvm install node && \
    nvm alias default node
```

Set the working directory inside the container
```
WORKDIR /app
```

Copy the package.json and package-lock.json files to the container
```
COPY package*.json ./
```

Install dependencies
```
RUN npm install --production
```

Copy the rest of the application files to the container
```
COPY . .
```

Build SvelteKit app
```
RUN npm run build
```

Expose the port that the app is running on
```
EXPOSE 3000
```

Command to start the application
```
CMD ["npm", "run", "dev", "--", "--open"]
```

# Docker Compose

## Traefik
The Traefic service has a dependency to the socket_proxy added later. It is configured with persistent volumes. Ports, entry points and some basic configurations are also added.

## Fastapi
Is assigned to the Traefic network and reachable on port 8085

## Mongodb
The mongodb database can be reached on port 27017.

## Socket_proxy
It proxies Docker socket requests to support container orchestration tools like Docker Compose, setting environment variables for networking and container information, exposing port 2, and mounting the Docker socket file as read-only inside the container. Finally, it connects the container to a network named "socket_proxy" To which Traefic also connects.

## Influx_db

Runs on port 8086 and also has persistent volumes for storing data.
