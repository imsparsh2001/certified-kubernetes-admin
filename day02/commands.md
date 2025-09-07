<!-- Important commands  -->

<!-- Docs -->
kubectl explain pod

<!-- Create a pod -->
kubectl run pod pod_name --image=nginx
kubectl apply -f pods.yaml 

<!-- List pods -->
kubectl get pods 
kubectl get pods -o wide 

<!-- Inspect and edit -->
kubectl describe pod pod_name 
kubectl edit pod pod_name 

<!-- Generate pod manifest (YAML) -->
kubectl run pod nginx --image=nginx:latest --dry-run=client -o yaml > pod.yaml

<!-- Exec into a pod -->
kubectl exec -it pod_name -- sh

<!-- Delete a pod by name -->
kubectl delete pod pod_name

<!-- Delete multiple pods -->
kubectl delete pod pod1 pod2
