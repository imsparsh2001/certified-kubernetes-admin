# Kubernetes Taints and Tolerations Commands 📝

This file collects all the important commands we used so far while exploring taints and tolerations in Kubernetes.

---

## 🔍 Check Node Taints
```bash
kubectl get nodes -o custom-columns=NAME:.metadata.name,TAINTS:.spec.taints
kubectl describe node <node-name> | sed -n '/Taints/,+3p'
```

---

## 🚫 Add Taints to Nodes
```bash
# Taint worker01 to allow only pods tolerating gpu=true:NoSchedule
kubectl taint nodes worker01 gpu=true:NoSchedule

# Taint worker02 with gpu=false:NoSchedule
kubectl taint nodes worker02 gpu=false:NoSchedule

# Taint control plane node back after testing
kubectl taint nodes local-control-plane node-role.kubernetes.io/control-plane=:NoSchedule
```

---

## 🧹 Remove Taints from Nodes
```bash
# Remove taint from worker node
kubectl taint nodes worker01 gpu=true:NoSchedule-

# Remove taint from control plane node
kubectl taint nodes local-control-plane node-role.kubernetes.io/control-plane-
# (older clusters may use this)
kubectl taint nodes local-control-plane node-role.kubernetes.io/master-
```

