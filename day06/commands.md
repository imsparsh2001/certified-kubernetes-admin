<!-- Important commands -->

kubectl apply -f daemonset.yaml

kubectl get daemonsets
kubectl describe pod <pod_name>
kubectl delete pod <pod_name>
<!-- Daemonset will make sure even if we delete the pod it will automaticlly detect it and restart the pods on each nodes present inside the cluster  -->
<!-- kubeproxy daemonset -->



