## cert-manager Configuration

This directory contains example configurations for cert-manager, used for automated TLS certificate management in the homelab Kubernetes environment.

cert-manager integrates with Let's Encrypt to issue and renew certificates, enabling secure (HTTPS) access to services exposed via Traefik.

### Files

- `cert-manager-clusterissuer.yaml`  
  Defines a ClusterIssuer using the ACME protocol with Let's Encrypt.  
  Configured to use a DNS-01 challenge via Cloudflare, allowing automatic certificate issuance for domain-based services.

- `cert-manager-values.yaml`  
  Helm values used during deployment of cert-manager.  
  Enables CRDs and configures DNS resolution for ACME challenges.

### Notes

- TLS certificates are automatically provisioned and renewed using Let's Encrypt
- DNS-01 challenge is used for domain validation via Cloudflare
- Sensitive data (e.g. API tokens) is stored separately as Kubernetes Secrets and is not included in this repository
- All configurations are simplified and sanitized for demonstration purposes