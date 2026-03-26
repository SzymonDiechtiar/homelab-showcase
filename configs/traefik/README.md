## Traefik Configuration

This directory contains example configurations for Traefik, used as the ingress controller in the homelab Kubernetes cluster.

Traefik is responsible for routing external traffic to internal services and enforcing secure (HTTPS) access.

### Files

- `traefik-values.yaml`  
  Core configuration for Traefik.  
  Defines entrypoints and enforces HTTPS by redirecting all HTTP traffic to secure endpoints.

- `traefik-dashboard-ingressroute.yaml`  
  Example of exposing a service using Traefik's IngressRoute custom resource.  
  Demonstrates hostname-based routing and integration with TLS.

- `dashboard-certificate.yaml`  
  Example TLS certificate resource used by Traefik-exposed services.  
  Certificates are issued and managed via cert-manager.

### Example Deployment

Traefik can be deployed using Helm with the provided values file:

```bash
helm install traefik traefik/traefik \
  --namespace traefik \
  --create-namespace \
  -f traefik-values.yaml

### Notes

- All configurations are simplified and sanitized for demonstration purposes
- TLS certificates are provisioned using cert-manager
- In a production setup, access to the Traefik dashboard should be restricted (e.g. authentication or IP whitelisting)