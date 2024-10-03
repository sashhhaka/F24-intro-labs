## Task 1: Artifact Registries Research

### 1. **Research Artifact Registries**:
Key idea of these services: Store, manage, and secure user container images.
#### 1. **AWS Artifact Registries**:
**Amazon Elastic Container Registry (ECR)**: https://aws.amazon.com/ru/ecr/

or **AWS CodeArtifact**: https://aws.amazon.com/ru/codeartifact/

#### 2. **Google Cloud Platform (GCP) Artifact Registries**:
**Google Cloud Artifact registry**: https://cloud.google.com/artifact-registry/docs

#### 3. **Azure Artifact Registries**:
**Azure Container Registry**: https://azure.microsoft.com/en-us/products/container-registry

or **Azure Artifacts**: https://azure.microsoft.com/en-us/products/devops/artifacts


#### **Comparison of Artifact Registries**

| Feature                               | Amazon ECR                    | AWS CodeArtifact     | GCP Artifact Registry          | Azure Container Registry (ACR) | Azure Artifacts     |
|---------------------------------------|-------------------------------|----------------------|--------------------------------|--------------------------------|---------------------|
| **Company**                           | Amazon Web Services (AWS)      | Amazon Web Services (AWS)   | Google Cloud                   | Microsoft Azure                | Microsoft Azure              |
| **Primary Use Case**                  | Docker containers              | Universal package management| Docker & multi-format packages | Docker containers              | Universal package management |
| **Supported Formats**                 | Docker images                  | npm, Maven, PyPI, NuGet | Docker, Maven, npm, PyPI       | Docker, OCI, Helm              | npm, Maven, NuGet, Python |
| **Integration with DevOps platforms** | AWS CodeBuild, CodeDeploy      | AWS CodeBuild, CodePipeline | GCP Build, GKE                 | Azure Pipelines                | Azure Pipelines     |
| **Vulnerability Scanning**            | Yes (image scanning)           | No (use 3rd-party tools) | Yes (image scanning)           | Yes (Microsoft Defender)       | No (use 3rd-party tools) |
| **Geo-Replication**                   | Yes                            | No                    | Yes                            | Yes                            | No                  |
| **Access Control**                    | IAM                            | IAM                   | IAM                            | Azure Active Directory         | Azure Active Directory |
| **External Repositories**             | No                             | Yes (third-party support) | Yes                            | No                             | Yes (with upstream sources) |
| **Lifecycle Management**              | Yes                            | No                    | Yes                            | Yes                            | No                  |

Legend to explain criteria:
- **Vulnerability Scanning**: Indicates whether the registry provides built-in security scanning to detect vulnerabilities in artifacts.

- **Geo-Replication**: Describes whether the registry supports automatic replication of artifacts across different geographic regions.

- **Access Control**: The system used to manage and restrict access to the registry and its contents.

- **External Repositories**: Refers to whether the registry supports connecting to external sources to fetch dependencies.

- **Lifecycle Management**: Describes whether the registry provides features to automate the cleanup of old or unused artifacts.

---
## Summary

- **Amazon ECR** and **Azure Container Registry (ACR)** focus mainly on managing Docker container images with features like geo-replication, image scanning, and integration with their respective cloud CI/CD services.
- **AWS CodeArtifact** and **Azure Artifacts** are more suitable for managing multiple package formats (npm, Maven, NuGet, PyPI) and are well-integrated with their respective DevOps tools. They are ideal for organizations managing various package dependencies.
- **GCP Artifact Registry** provides a unified platform supporting both container images and multiple package formats, making it versatile and efficient for hybrid use cases.

---


## Task 2: Serverless Computing Platform Research
Key idea of these services: Develop and deploy highly scalable containerized applications on a fully managed serverless platform.
### 1. **Research Best Serverless Computing Platforms**:
#### 1. **AWS Serverless Computing Platforms**: https://aws.amazon.com/serverless/
**AWS App Runner**: https://aws.amazon.com/apprunner/

**AWS Lambda**: https://aws.amazon.com/lambda/?c=ser&sec=srv

**AWS Fargate**: https://aws.amazon.com/fargate/?c=ser&sec=srv

#### 2. **Google Cloud Platform (GCP) Serverless Computing Platforms**: https://cloud.google.com/discover/what-is-serverless-computing?hl=ru#related-products-and-services
**Cloud Run**: https://cloud.google.com/run?hl=ru

#### 3. **Azure Serverless Computing Platforms**: https://azure.microsoft.com/en-us/solutions/serverless/
**Azure Container Apps**: https://azure.microsoft.com/en-us/products/container-apps

**Azure Container Instances**: https://azure.microsoft.com/en-us/products/container-instances

#### Comparison of Serverless Computing Platforms

| Feature                            | AWS App Runner                | AWS Lambda                | AWS Fargate                  | Google Cloud Run              | Google Cloud Functions        | Azure Container Apps          | Azure Container Instances      |
|------------------------------------|-------------------------------|---------------------------|------------------------------|------------------------------ |-------------------------------|-------------------------------|-------------------------------|
| **Company**                        | Amazon Web Services (AWS)      | Amazon Web Services (AWS) | Amazon Web Services (AWS)     | Google Cloud                  | Google Cloud                  | Microsoft Azure               | Microsoft Azure               |
| **Primary Use Case**               | Containerized web apps         | Event-driven functions    | Containerized apps and tasks  | Containerized apps and APIs   | Event-driven functions         | Containerized microservices   | Containerized apps            |
| **Container Support**              | Yes                           | Yes                       | Yes                          | Yes                           | No                            | Yes                           | Yes                           |
| **Auto Scaling**                   | Yes                           | Yes                       | Yes                          | Yes                           | Yes                           | Yes                           | Yes                           |
| **Pay-Per-Use**                    | Yes                           | Yes (per invocation)      | Yes                          | Yes                           | Yes (per invocation)           | Yes                           | Yes                           |
| **Startup Time**                   | Fast (optimized for HTTP apps) | Milliseconds              | Seconds (task-specific)       | Fast (optimized for HTTP apps) | Milliseconds                  | Fast (HTTP/microservice apps) | Seconds                       |
| **Orchestration**                  | No                            | Yes                       | Yes (with ECS/EKS)            | Yes (Knative)                 | Yes                           | Yes (with Dapr)                | No                            |
| **Language Support**               | Any (containerized)            | Python, Node.js, Java, Go | Any (containerized)           | Any (containerized)            | Python, JavaScript, Go, Java   | Any (containerized)            | Any (containerized)            |
| **Built-in Security**              | Yes                           | Yes                       | Yes                          | Yes                           | Yes                           | Yes                           | Yes                           |


Legend to explain criteria:
- **Container Support**: Indicates whether the platform supports running containerized applications.
- **Auto Scaling**: Describes whether the platform automatically scales resources based on demand.
- **Pay-Per-Use**: Indicates whether the platform charges based on actual usage.
- **Startup Time**: Refers to the time taken to start a new instance or function.
- **Orchestration**: Describes whether the platform supports orchestrating complex workflows or microservices.
- **Language Support**: Lists the programming languages supported by the platform.
- **Built-in Security**: Indicates whether the platform provides built-in security features such as automatic updates, security patches, or built-in compliance checks.

---

## Summary

- **AWS** (Amazon Web Services): Offers three primary serverless platforms — **AWS Lambda** for event-driven compute, **AWS App Runner** for containerized web applications, and **AWS Fargate** for containerized apps and tasks, all of which integrate seamlessly into AWS services.
  
- **Google Cloud**: Provides **Google Cloud Run** for running containerized apps, and **Google Cloud Functions** for event-driven functions, both of which scale automatically and are deeply integrated with Google's ecosystem.

- **Microsoft Azure**: Delivers **Azure Container Apps** and **Azure Container Instances** for containerized workloads. **Azure Container Apps** is particularly suited for microservices.

