export DOCKER_HOST=unix:///var/run/docker.sock

docker build --tag python-docker-image .
docker run -p 5000:5000 python-docker-image