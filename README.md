# Monitor argocd gitops with a lightweight standalone prometheus 
1) Create a application in argo pointing to the git repo and the namespace (kubernetes on docker-desktop) 
   Argo CD syncs your Helm chart, Nginx deployed
   Argo CD exposes metrics via a dedicated service (argocd-metrics, argocd-repo-server-metrics, etc.)
2) Configure Prometheus to Scrape Argo CD Metrics.
3) Deploy Grafana + Argo CD Dashboards

# Replace the Helm binary bundled inside Argo CD with a different version of Helm
1) Build your own argocd-repo-server image with the desired Helm version baked in.
2) Push it to registry
3) Patch the deployment to use the custom image.  
