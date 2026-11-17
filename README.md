# TP 4 – Kubernetes: Multi-Node Cluster Deployment with kind

**Author:** Fatima Zohra Aalilouch  
**Program:** Computer Engineering – Software Engineering  
**Institution:** ENSA Al Hoceima  
**Academic Year:** 2026–2027  
**Module:** Virtualization, Cloud Computing & DevOps

---

## Project Overview

This project focuses on the practical implementation of Kubernetes fundamentals through the creation and management of a local multi-node cluster using **kind (Kubernetes in Docker)**.

It explores container orchestration, application deployment, service exposure, load distribution, automatic recovery, horizontal scaling, rolling updates, rollback mechanisms, and internal DNS resolution.

## Objectives

- Understand Kubernetes cluster architecture and its main components.
- Create and manage a multi-node Kubernetes cluster.
- Deploy containerized applications using Pods and Deployments.
- Expose applications using Kubernetes Services.
- Implement application scaling and self-healing.
- Perform rolling updates and rollbacks.
- Understand Kubernetes networking and internal DNS.

## Technologies & Tools

| Category | Technologies |
|---|---|
| Containerization | Docker, Docker Desktop |
| Orchestration | Kubernetes, kind |
| CLI Tools | kubectl, Helm |
| Configuration | YAML |
| Test Applications | Nginx, Traefik Whoami, BusyBox |
| Environment | Windows, PowerShell, WSL2 |

## Practical Implementation

### Part A – Multi-Node Cluster Creation

Created a local Kubernetes cluster using kind with:
- 1 Control Plane node.
- 2 Worker nodes.
- Port mapping: 30080.

### Part B – Pod Management

- Created an Nginx Pod.
- Inspected Pod status, logs, and configuration.
- Accessed the container using `kubectl exec`.
- Tested application access using port forwarding.
- Compared imperative and declarative Pod creation.

### Part C – Deployment and Service

- Created a Deployment with 3 replicas of Traefik Whoami.
- Exposed the application using a NodePort Service.
- Tested traffic distribution across replicas.
- Verified automatic Pod replacement after deletion.
- Scaled the Deployment from 3 to 6 replicas.
- Inspected Service EndpointSlices.

### Part D – Rolling Updates and Rollbacks

- Updated the application from version v1.10 to v1.11.
- Monitored the rollout process.
- Simulated a failed deployment using an unavailable image (v9.99).
- Observed `ErrImagePull` and `ImagePullBackOff`.
- Performed a rollback using `kubectl rollout undo`.
- Verified the recovery of the stable application version.

### DNS Challenge – Internal Service Discovery

Tested communication between Pods using the fully qualified domain name:

`whoami.default.svc.cluster.local`

Explored CoreDNS and Kubernetes internal service discovery.

## Repository Structure

```text
.
├── kind-config.yaml
├── pod.yaml
├── whoami.yaml
├── rollout-history.txt
├── compte-rendu/
│   └── TP4_Kubernetes_Compte_Rendu_AALILOUCH-Fatima-zohra.pdf
└── captures/
    └── Screenshots by implementation section
```

## Troubleshooting

During implementation, DNS resolution issues prevented Kubernetes nodes from downloading container images directly from Docker Hub.

The issue was handled by pulling images on the host machine, exporting them using `docker save`, and loading them into the kind cluster using `kind load image-archive`.

This allowed the practical exercises to continue successfully.

## Learning Outcomes

This hands-on project provided practical experience in:

- Kubernetes architecture and container orchestration.
- Declarative infrastructure management.
- Deployment lifecycle management.
- High availability and self-healing.
- Horizontal scaling and load distribution.
- Rolling updates and rollback strategies.
- Kubernetes networking and DNS resolution.
- Troubleshooting container image deployment issues.

## Detailed Report

The complete lab report, including implementation screenshots, command outputs, explanations, and answers to the theoretical questions, is available here:

[📄 Read the Full Kubernetes Lab Report (PDF)](compte-rendu/TP4_Kubernetes_Compte_Rendu_AALILOUCH-Fatima-zohra.pdf)
