DaemonSet
A DaemonSet ensures that a copy of a pod runs on every node in the Kubernetes cluster (or specific nodes you select). Typical use cases include running monitoring agents, log collectors, networking plugins, or control plane components which must be present on all nodes (like kube-proxy, CNI plugins such as Calico, Flannel, and Weave)

DaemonSets don't use the replicas field—Kubernetes ensures one pod per node. If a node joins or leaves the cluster, the DaemonSet adjusts itself automatically.

Job
A Job creates one or more pods that run to completion (finish their task and then terminate). Use a Job for batch or one-off tasks, like setup scripts or data migrations.

Once completed, Jobs don’t restart automatically unless configured with extra fields.

CronJob
A CronJob creates Jobs on a regular schedule, using UNIX cron syntax. Use cases include database backups, periodic reporting, clean-up tasks, and routine maintenance.

Cron Schedule Syntax Breakdown
Minute (0–59)

Hour (0–23)

Day of month (1–31)

Month (1–12)

Day of week (0–6, Sunday is 0)

Examples:

* * * * *: every minute

45 23 * * 6: at 11:45 PM each Saturday

