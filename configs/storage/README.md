## Storage Configuration

This directory contains example configurations for storage used in the homelab Kubernetes environment.

Storage is provided externally via an OpenMediaVault instance and integrated into the cluster using NFS.

### Files

- `nfs-pv.yaml`  
  Defines a PersistentVolume backed by an NFS share.  
  Represents external storage provided by the NAS and made available to the cluster.

- `nfs-pvc.yaml`  
  Example PersistentVolumeClaim used by applications to request storage from the NFS-backed volume.

### Notes

- Storage is managed outside of Kubernetes to provide greater flexibility and separation of concerns
- NFS allows shared access (**ReadWriteMany**) across multiple pods and services
- Applications (e.g. media services) use PersistentVolumeClaims to mount storage
- All configurations are simplified and sanitized for demonstration purposes