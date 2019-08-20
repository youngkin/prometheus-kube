# prometheus-kube

Deploys Promethues into a Kubernetes cluster. This repository supports 2 methods of deploying Prometheus:

1. Via standard Kubernetes commands (e.g., kubectl create)
1. Via Helm (using the charts located in 'prom-chart')

While both methods are supported, using Helm is preferred and is most up-to-date with respect to the paths required to support ingress from outside the cluster (via an ingress controller).

The charts and kube yaml files are up-to-date but untested. They were changed after troubleshooting that uncovered that the Prometheus app URLs weren't correctly represented in ingress config files (both Helm and standard Kube files). p9singresspatch.json contains the JSON text needed to run via the 'kubectl patch' command to correct the previously non-working deployment.
