# Install Docker
```
sudo apt-get update
sudo apt install docker.io
sudo apt install docker-compose
sudo chown $USER /var/run/docker.sock
```

# Login to Docker hub
docker login -u itcode -p 

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