# This is a repo for out new DevOps project


docker build --tag python-docker-image .
docker run -p 5000:5000 python-docker-image