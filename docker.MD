#   If Docker commands not running without SUDO
`
export DOCKER_HOST=unix:///var/run/docker.sock
echo $DOCKER_HOST
docker ps
`