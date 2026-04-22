# Kubernetes Learning Notes

## Day 0:

---

### Completed tasks:

- Watch introductory video on kubernetes
- Read overview (https://kubernetes.io/docs/concepts/overview/) on the official site

---

### Questions:

#### Why does kubernetes exist?

Kubernetes exists to orchestrate a large set of programs in the form of nodes.

Nodes contain pods which run the individual instances of applications, and inside each node is a set of processes that help manage accesses and configuration from a central control plane.

This centralizes the access of these nodes, allowing an admin to control each instance from one command line interface.

It also has a self healing characteristic, where deployed pods are rebooted based on their original images (configurations) if an instance were to go down.

The standard for a pod is described by the user, and kubernetes will heal the pod until it is ready to serve to the client.

How kubernetes creates or destroys pods are configurable, as well as the amount of resources to allocate to each node. Kubernetes will utilize those resources in the optimal way.

Furthermore, admins can configure secrets right in the configuration, and you can make changes to these without having to redeploy or rebuild your pods.

Kubernetes also orchestrates storage and load balances incoming traffic between the deployed nodes so that no one instance is overloaded. This ensures that the system is stable and all tasks are handled.

You can describe the state of the deployed pods, and kubernetes will automatically migrate the pods toward the state in a controlled manner.

Kubernetes can also manage batch execution and CI workloads. It can also scale based on your command or automatically based on CPU usage (if desired).

It supports IPv4 and IPv6.

You can add features to your Kubernetes cluster without changing upstream source code.

