## Task 

In this exercise, you will explore health probes in Kubernetes


### Task details
1.
- Login to your cluster and create a pod with the image name as registry.k8s.io/busybox
- use the below command for the container
  `touch /tmp/healthy; sleep 30; rm -f /tmp/healthy; sleep 600`
- create a livenessprobe that executes the command `cat /tmp/healthy` after every 5 seconds, the first check should be after 5 seconds
- create another pod with the image name as `registry.k8s.io/e2e-test-images/agnhost:2.40`
- add the liveness and readiness probes that perform health checks on port 8080 on the path /healthz , the checks should start after 5 seconds for every 10 seconds

