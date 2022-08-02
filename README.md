# NEXTJS Dockerize Boilerplate 

It uses for dockerize nextjs app, quick setup of the server enviroment and deploy an app to the server.

## Install Docker
```
sudo apt-get update
sudo apt install docker.io
sudo apt install docker-compose
sudo chown $USER /var/run/docker.sock
```

## Clone GIT repository
```
mkdir /home/ubuntu/srv
cd /home/ubuntu/srv
git clone https://github.com/itcodeio/nextjs_dockerize.git .
```

## Login to Docker hub
docker login -u itcode -p [password]

## Set env param
```
cp .env.sample .env
vim .env
```
e.g.

```
NEXTJS_DOCKER_REPOSITORY=itcode/[projectname]:[tagname]
```

## Run docker containers
```
docker-compose up -d --build --force-recreate
```

## Prepare project configuration
Review example folder and select solution: docker only or docker with pm2.
Copy files from example folder to your project folder.

```
cp example/.dockerignore ./[:poject_folder]
cp example/[:solution]/Dockerfile ./[:poject_folder]
```

Then exeecute the following commands
```
docker login -u itcode -p [password]
docker build . -t itcode/[projectname]:[tagname]
docker push itcode/[projectname]:[tagname]
```