# app-repo
For application code

CI/CD Workflow
Developer Workflow:

Developer makes code changes to the app-repo
Updates are pushed to GitHub
CI Pipeline (GitHub Actions):

Test: Runs tests to ensure code quality
Build: Extracts version from package.json and builds a Docker image
Push: Pushes the Docker image to Docker Hub with the version tag
Update Manifest: Updates the image version in the deployment manifest in manifests-repo
CD Pipeline (ArgoCD):

ArgoCD continuously monitors the manifests-repo
When changes are detected, ArgoCD automatically applies them to the Kubernetes cluster
The updated application is deployed with zero downtime

