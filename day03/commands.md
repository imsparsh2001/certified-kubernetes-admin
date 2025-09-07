<!-- Important commands  -->

<!--  Docs -->
kubectl explain replicaset
kubectl explain deployment
# (Optionally: kubectl explain deployment.spec.template.spec.containers)

<!-- Apply -->
kubectl apply -f replicaset.yaml
kubectl apply -f deployment.yaml

<!-- List -->
kubectl get rs
kubectl get deploy         
kubectl get deployments

<!-- Edit live objects -->
kubectl edit rs/nginx-rs
kubectl edit deploy/nginx-deployment

<!-- Scale a ReplicaSet  -->
kubectl scale --replicas=5 rs/nginx-rs
kubectl scale --replicas=5 deploy/nginx-deployment

<!-- Describe  -->
kubectl describe rs/rs_name
kubectl describe deploy/deployment_name

<!-- Update image on a Deployment -->
kubectl set image deploy/nginx-deploy nginx=nginx:latest

<!-- Rollouts -->
kubectl rollout history deploy/nginx-deploy
kubectl rollout undo deploy/nginx-deploy

<!-- Create a Deployment YAML -->
kubectl create deploy nginx-deploy --image=nginx:latest --dry-run=client -o yaml > dpl.yaml


<!-- Delete a deployment by name -->
kubectl delete deploy deployment_name

<!-- Delete multiple deployments -->
kubectl delete deploy deploy1 deploy2