# Docker Compose
I followed these instruction
https://semaphoreci.com/community/tutorials/dockerizing-a-ruby-on-rails-application
and i made my docker-compose.yml and up my application
i passed environment variable not by .env, i put it in docker-compose.yml
i published all my images genereted from dockerfiles to my docker hub.

# Migrate to Kubernates from Docker-Compose
  
  I'm Using Minikube
  I edited docker-compose.yml to use it with kompose conversion tool 
  THEN i convert my docker-compose.yml to k8s-manifests 
  I created configmap and use it as .env file, then i created k8s resources
  I passed command to drkiq running pod to create/migrate database
    $ kubectl exec drkiq_pod rake db:create
  I used NodePort to access my app by enabling minkube ingress-controller 
    $ minikube addons enable ingress
    then created ingress.yaml and apply it
    and generate link to access my app by $ minikube service drkiq-nginx --url
  
  
  
  
  
