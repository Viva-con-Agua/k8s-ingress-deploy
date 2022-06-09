# Deployment configuration for Kubernetes Ingress Controller

![Deployment Status](https://argocd.vivaconagua.org/api/badge?name=k8s-ingress&revision=true)

This repository consists of kubernetes manifests that deploy an Ingress Controller on our infrastructure the way we want it to.

## Configuration Details

We use the [Kubernetes NGINX Ingress Controller](https://kubernetes.github.io/ingress-nginx/) as ingress implementation.
It is deployed over a [NodePort Service](https://kubernetes.github.io/ingress-nginx/deploy/baremetal/#over-a-nodeport-service) (ports `30080` and `30443`) on all our servers and accessed from the internet through a Hetzner load balancer.

The Controller configuration is done through the file [config.env](./config.env).
All HTTP headers defined in [headers.env](./headers.env) are also automatically set on all outgoing HTTP responses.
