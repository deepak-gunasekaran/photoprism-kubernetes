# Kubernetes PhotoPrism
Photoprism with MariaDB on K8

## Requirements
* A functional k8s cluster 
* [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
* [Kustomize](https://github.com/kubernetes-sigs/kustomize)
* An HTTPS enabled proxy in front of the k8s cluster (e.g: [nginx with Let's Encrypt](https://www.nginx.com/blog/free-certificates-lets-encrypt-and-nginx/))

## Deployment
* Update mariadb/secret.yaml with MYSQL_PASSWORD and MYSQL_ROOT_PASSWORD (can be set to anything, must be base64 encoded) 
* Update photoprism/ingress.yaml with your kubernetes domain name
* Adjust storage size in photoprism/pvc.yaml and pv-app.yaml to fit your needs 
* (Optional) To preview generated configuration before deploying:
        `kustomize build -o final-deployment.yaml` 
* Run the following command to build and deploy

        kustomize build | kubectl apply -f -
         
