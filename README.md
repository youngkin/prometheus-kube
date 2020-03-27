# prometheus-kube

Deploys Promethues into a Kubernetes cluster. To get a fully working Prometheus deployment:

1. `kubectl create ns monitor`
2. Complete the deployment via `helm install --namespace default --name prometheus prom-chart` from the project root directory.

To verify the deployment:

1. `http://prom.kube` in a browser
![Prometheus expression graphing tab](./docs/prom.kube-graph.jpg)
1. In the top navigation bar, click ***Status*** and select ***Targets*** from the dropdown (`http://prom.kube/targets`) 
![Prometheus expression graphing tab](./docs/prom.kube-targets.jpg)
    All targets should show an "UP" `State`
