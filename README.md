# Kubernetes Gateway API & ALB Controller Lab

This repository serves as a practical laboratory designed to help developers and DevOps engineers understand the modern Kubernetes stack. It focuses on replacing the traditional Ingress API with the **Gateway API** standard, utilizing the **AWS Load Balancer (ALB) Controller** as the implementation.

The project leveraging **Helmfile** for chart orchestration, **Kustomize** for manifest patching, and **Kro** for creating custom Kubernetes APIs.

## 🚀 Project Overview

The main goal of this lab is to demonstrate how multiple microservices can share a single Application Load Balancer (ALB) through the Gateway API, reducing costs and simplifying traffic management.

### Tech Stack
* **Kubernetes Gateway API:** The evolution of Kubernetes networking.
* **AWS Load Balancer Controller:** The controller that provisions AWS ALBs based on Gateway API resources.
* **Helmfile:** Declarative specification for deploying Helm charts.
* **Kustomize:** Configuration management for native Kubernetes manifests.
* **Kro:** A tool to define simplified Custom Resource Definitions (CRDs) and ResourceGroups (RGD) to abstract complexity for microservices.
* **Nginx:** Used as the base image for the demo microservices (`mondamail` and `mondareader`).

## 📂 Repository Structure

The repository is organized into infrastructure management and application logic:

```text
.
├── infrastructure
│   ├── helm               # Helmfile configuration
│   │   ├── charts         # Configurations for ALB, Gateway API, and Kro
│   │   └── helmfile.yaml  # Main entry point for infrastructure deployment
│   └── kustomize          # Raw manifests and overlays
│       ├── base           # Base definitions (Gateway, ALB ServiceAccount, Kro RGDs)
│       └── overlays       # Environment-specific patches (dev/prod)
└── microservices          # Demo applications
    ├── mondamail          # Example microservice 1
    └── mondareader        # Example microservice 2
```