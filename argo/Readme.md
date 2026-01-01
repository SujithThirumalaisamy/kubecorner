## Disable Internal TLS (Argo CD)

To avoid internal HTTP ↔ HTTPS redirection loops, run the Argo CD API server with TLS disabled.

### Option 1: Using ConfigMap (Recommended)

Update the `argocd-cmd-params-cm` ConfigMap:

```yaml
server.insecure: "true"
```

Restart the `argocd-server` pod after applying the change.

### Option 2: Using Deployment

Edit the `argocd-server` Deployment and add the `--insecure` flag to the `argocd-server` container arguments.

Restart the `argocd-server` pod for the changes to take effect.
