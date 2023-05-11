# ArgoCD Project

This project is designed to manage deployments using ArgoCD, a declarative, GitOps continuous delivery tool for Kubernetes.

## Project Structure

The project has a specific structure, designed for maintaining base Kubernetes configurations and specific environment settings.

```
.
└── devsu
    ├── base
    │   ├── deployment.yml
    │   ├── service.yml
    │   ├── ingress.yml
    │   └── secret.yml
    └── settings
        ├── deployment-patch.yml
        ├── service-patch.yml
        ├── ingress-patch.yml
        └── secret-patch.yml
```

### Base

This directory contains the base Kubernetes configuration files. These are the fundamental building blocks for your application and define the Kubernetes resources required.

- **deployment.yml**: Defines the deployment for the application.
- **service.yml**: Sets up the service to expose the application.
- **ingress.yml**: Configures the ingress for the application.
- **secret.yml**: Stores any secrets that your application needs.

### Settings

This directory contains patch files for each base configuration. These files allow you to define environment-specific settings.

- **deployment-patch.yml**: Contains changes to the base deployment configuration.
- **service-patch.yml**: Contains changes to the base service configuration.
- **ingress-patch.yml**: Contains changes to the base ingress configuration.
- **secret-patch.yml**: Contains changes to the base secret configuration.

These patch files are applied on top of the base files to create the final configuration that ArgoCD interprets when setting up the cluster.

## Usage

ArgoCD will use the configuration files in this repository to manage the Kubernetes resources. When a commit is made to this repository, ArgoCD will automatically sync the changes to the cluster, applying any patches as needed. This allows you to manage your cluster configuration in a declarative manner, following the GitOps methodology.

## Contribute

Please make sure to update tests as appropriate. For any changes, make a pull request.

## License
Copyright © 2023 Devsu. All rights reserved.
