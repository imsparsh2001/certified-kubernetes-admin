Kubernetes Taints and Tolerations

Taints and tolerations work together to control which pods can be scheduled on which nodes. They’re like access control for your cluster’s resources.

🚫 Taints: Putting Up Fences

A taint is like a "Keep Out" or "Special Access Only" sign you attach to a node.

By default, pods cannot be scheduled on tainted nodes.

Taints are defined with a key, optional value, and an effect.

Example: Add a taint
kubectl taint nodes node1 gpu=true:NoSchedule


key: gpu

value: true

effect: NoSchedule

Pods without a matching toleration will not be scheduled on node1.

Remove a taint
kubectl taint nodes node1 gpu=true:NoSchedule-


Notice the - at the end — it deletes the taint.

✅ Tolerations: Permission Slips for Pods

A toleration is like a hall pass for a pod. It tells Kubernetes:
"I can handle this taint, it’s okay to put me there."

Example: Pod tolerating a taint
apiVersion: v1
kind: Pod
metadata:
  name: redis
  labels:
    run: redis
spec:
  containers:
  - name: redis
    image: redis
  tolerations:
  - key: "gpu"
    operator: "Equal"
    value: "true"
    effect: "NoSchedule"


This pod tolerates the gpu=true:NoSchedule taint and can therefore run on a node with that taint.

🎬 Taints & Tolerations in Action

Add taint to node

kubectl taint nodes worker01 gpu=true:NoSchedule


Create pod without toleration → it will not schedule on that node.

Add toleration to pod spec → pod now runs on the tainted node.

Remove taint from node → any pod can be scheduled there again.

🏷️ Labels vs. Taints

Labels: Group and organize nodes (e.g., env=prod, type=large).
They don’t restrict scheduling by themselves.

Taints + Tolerations: Restrict scheduling — pods must explicitly tolerate taints to be scheduled.

⚠️ Limitations

Taints/tolerations are simple key/value matches.

They can’t express complex logic (AND, OR).

For advanced scheduling, combine:

Taints/Tolerations (restrictions)

Node Affinity (preferences/requirements)