Deploy node app which connects to redis

# Requirements
1. minikube
2. kubectl
3. ingress addon `minikube addons enable ingress`
4. optionally k9s

# Steps

## Creating the docker image
1. `docker build ./server -t isaac/nodejs-server`
2. `docker run isaac/nodejs-server`
3. `curl localhost:3000`
You should received an api response

## Deploying nodejs server
1. Use local docker repository `eval $(minikube -p minikube docker-env)`
2. `kubectl create -f ./server/Deployment.yaml`
3. `kubectl create -f ./server/Service.yaml`
4. `kubectl create -f ./server/Ingress.yaml`

## Expose the ingress external ip address for the dns
1. sudo vim /etc/hosts
  ```
  192.168.64.2 example-server.info
  ```
2. curl example-server.info
