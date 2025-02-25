# Development Environment Kustomization

This directory contains Kubernetes configuration patches specific to the development environment.

## Structure
```
overlays/dev/
├── kustomization.yaml         # Main kustomization file
└── patches/                   # Directory containing all patches
    ├── frontend-deployment.yaml  # Frontend deployment patches
    ├── backend-deployment.yaml   # Backend deployment patches
    ├── backend-configmap.yaml    # Backend application config
    └── ingress.yaml              # Ingress configuration
```

## Usage

```bash
# Preview configurations
kubectl kustomize overlays/dev

# Apply to cluster
kubectl apply -k overlays/dev
```

## Configuration Details

1. **Frontend Deployment** - Sets the image for the user interface
2. **Backend Deployment** - Sets the image and resources for the events backend
3. **Backend ConfigMap** - Configures the Spring Boot application for development
4. **Ingress** - Sets up routes for both the frontend and API

## Secrets

Secrets are generated automatically using the `secretGenerator` in kustomization.yaml. For production, consider using a more secure secret management solution.