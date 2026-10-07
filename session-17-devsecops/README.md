# Session 17: Complete CI/CD & DevSecOps

## DevSecOps Demo Project
Integrated security checks into the CI/CD pipeline.

- **Application & Dockerfile**: [App Code & Dockerfile](https://github.com/Anushika06/CI-CD-Pipeline)
- **Kubernetes Manifests**: [k8s Manifests](https://github.com/Anushika06/CI-CD-Pipeline/tree/main/k8s)
- **GitHub Actions Workflow**: [DevSecOps Pipeline YAML](https://github.com/Anushika06/CI-CD-Pipeline/blob/main/.github/workflows/devsecops.yml)

### Security Tools Configuration
- **SAST**: GitHub CodeQL
- **SCA**: pip-audit
- **Secret Scanning**: GitHub Secret Scanning / Trivy
- **Container Image Scanning**: Trivy

## Pipeline Flow
Code -> Build -> Unit Test -> SAST -> SCA -> Secret Scan -> Docker Build -> Container Image Scan -> Security Gate -> Push Image -> Deploy to Kubernetes.

![Pipeline Success](https://raw.githubusercontent.com/Anushika06/CI-CD-Pipeline/main/image.png)


