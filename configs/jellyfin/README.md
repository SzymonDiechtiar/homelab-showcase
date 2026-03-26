## Jellyfin Deployment

This directory contains example Kubernetes manifests used to deploy Jellyfin within the homelab environment.

Jellyfin is a self-hosted media server, deployed in the k3s cluster and exposed securely via Traefik.

### Files

- `jellyfin-deployment.yaml`  
  Defines the Jellyfin application deployment.  
  Includes container configuration, environment variables, and persistent storage mounts.

- `jellyfin-service.yaml`  
  Exposes the Jellyfin pod internally within the cluster using a ClusterIP service.

- `jellyfin-ingressroute.yaml`  
  Configures external access to Jellyfin via Traefik.  
  Uses hostname-based routing and integrates with TLS for secure access.

### Notes

- Persistent storage is provided via Kubernetes PersistentVolumeClaims
- The application runs with a non-root user for improved security
- External access is routed through Traefik and secured using TLS certificates issued by cert-manager
- All configurations are simplified and sanitized for demonstration purposes