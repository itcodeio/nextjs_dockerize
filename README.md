# Install Docker
```
sudo apt-get update
sudo apt install docker.io
sudo apt install docker-compose
sudo chown $USER /var/run/docker.sock
```

# Clone git repository
```
mkdir /home/ubuntu/srv
cd /home/ubuntu/srv
git clone https://github.com/itcodeio/nextjs_dockerize.git .
```

# Login to Docker hub
docker login -u itcode -p [password]

# Set env param
```
cp .env.sample .env
vim .env
```
e.g.

```
NEXTJS_DOCKER_REPOSITORY=itcode/[projectname]:[tagname]
```

# Run docker containers
```
docker-compose up -d --build --force-recreate
```

# Prepare project configuration
Copy files from example folder to your project folder (see example folder)
Then exeecute the following commands
```
docker login -u itcode -p [password]
docker build . -t itcode/[projectname]:[tagname]
docker push itcode/[projectname]:[tagname]
```