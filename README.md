# prometheus-kube

Deploys Promethues into a Kubernetes cluster. This repository _almost_ supports 2 methods of deploying Prometheus:

1. Via standard Kubernetes commands (e.g., `kubectl create`)
1. Via Helm (using the charts located in `prom-chart`)

The intent is for both methods to be supported, but neither the current configuration of Helm-only nor the `k create -f ...` approaches on their own will create a working Prometheus deployment. To get a fully working Prometheus deployment:

1. Deploy the ConfigMap, and SA/ClusterRole/ClusterRoleBinding via the `k create -f ...` method. The associated files are `prometheus-config-map.yml`, and `clusterrole2.yaml`.
1. Complete the deployment via `helm install --namespace default --name prometheus prom-chart` from the project root directory.

To verify the deployment:

1. `http://prom.kube/graph` in a browser
![Prometheus expression graphing tab](./docs/prom.kube-graph.jpg)
1. `http://prom.kube/targets` in a browser
![Prometheus expression graphing tab](./docs/prom.kube-targets.jpg)
    All targets should show an "UP" `State`
