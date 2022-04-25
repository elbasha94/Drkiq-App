# Docker Compose
- I followed instruction you mentioned: 
   * https://semaphoreci.com/community/tutorials/dockerizing-a-ruby-on-rails-application
- made my docker-compose.yml and up my application
- passed environment variable not by .env, i put it in docker-compose.yml
- published all my images genereted from dockerfiles to my docker hub.

# Migrate to Kubernates from Docker-Compose
  
  - I'm Using Minikube
  - edited docker-compose.yml to use it with kompose conversion tool 
    * docker-compose.yml in k8s-manifests directory, its a file i used to kompose convert.
  - THEN i convert my docker-compose.yml to k8s-manifests 
  - created configmap and use it as .env file, then i created k8s resources
  - passed command to drkiq running pod to create/migrate database
    * $ kubectl exec drkiq_pod rake db:create
  - used NodePort to access my app by enabling minkube ingress-controller 
    * $ minikube addons enable ingress
  - then created ingress.yaml and apply it
  - Finally generate link to access my app by *$ minikube service drkiq-nginx --url
  
  
  
  
  
