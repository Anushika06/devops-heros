# Session 15: Helm

## Task 1: Helm Commands
Executed essential Helm commands (`create`, `install`, `list`, `status`, `upgrade`, `rollback`, `uninstall`, etc.).

### 01 What is Helm
![what is helm 1](01-what-is-helm/image.png)
![what is helm 2](01-what-is-helm/image-1.png)

### 02 Helm Charts
![helm charts 1](02-helm-charts/image.png)
![helm charts 2](02-helm-charts/image-1.png)
![helm charts 3](02-helm-charts/image-2.png)

### 03 Chart Structure
![chart structure 1](03-chart-structure/image.png)
![chart structure 2](03-chart-structure/image-1.png)

### 07 Install Upgrade
![install upgrade 1](07-install-upgrade/image.png)
![install upgrade 2](07-install-upgrade/image-1.png)
![install upgrade 3](07-install-upgrade/image-2.png)

## Task 2: Helm Rollback
Successfully performed the rollback workflow:

![alt text](image.png)

## Task 3: Mini Project
- **Helm Chart**: [notes-chart](mini-project/notes-chart)
- **values.yaml**: [values.yaml](mini-project/notes-chart/values.yaml) and [values-prod.yaml](mini-project/notes-chart/values-prod.yaml)
- **Templates**: [templates directory](mini-project/notes-chart/templates) (Deployment, Service, ConfigMap)
- **Installation & Upgrade**: Installed dev version, then successfully upgraded using `values-prod.yaml` to scale up to 3 replicas.
- **Rollback**: Simulated a bad upgrade with an invalid image tag resulting in ImagePullBackOff, then successfully performed a rollback (`helm rollback`) to a healthy state.

![alt text](image-1.png)
![alt text](image-2.png)
![alt text](image-3.png)