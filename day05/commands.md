<!-- Important commands  -->


kubectl get namespace 
kubectl get all -n kube-system 
<!-- by default it will show the default namespace  -->

kubectl create deploy nginx-demo --image=nginx -n testing-namespace 
kubectl get deploy 
kubectl get deploy -n testing-namespace 