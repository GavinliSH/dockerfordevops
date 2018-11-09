docker build -t go-agent:gradle .

docker run -itd --name go-agent-1 -e GO_SERVER_URL=https://$(docker inspect --format='{{(index (index .NetworkSettings.IPAddress))}}' go-server-1):8154/go go-agent:gradle