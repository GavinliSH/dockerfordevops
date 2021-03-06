### Docker installation:
Download rpm package:`https://yum.dockerproject.org/repo/main/opensuse/13.2/Packages/`

Install docker use rpm package
```
zypper install
``` 
Config repository
```
vi /etc/docker/daemon.json
```
### build/run containers
#### sonarqube
```
docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
```
#### go-server
##### run
```
docker run -d -p8153:8153 -p8154:8154 --name go-server-1 gocd/gocd-server:v18.10.0
```
#### go-agent:gradle
##### build
```
docker build -t go-agent:gradle ./gocd-agent-gradle
```
##### run
```
docker run -itd --name go-agent-1 -e GO_SERVER_URL=https://$(docker inspect --format='{{(index (index .NetworkSettings.IPAddress))}}' go-server-1):8154/go go-agent:gradle
```
### Images
#### docker save images
```
docker save -o sonarqube.tar sonarqube
docker save -o gocd.tar gocd
docker save -o go-agent-gradle.tar go-agent:gradle
```

####load images
```
docker load -i sonarqube.tar
docker load -i gocd.tar 
docker load -i go-agent-gradle.tar
```