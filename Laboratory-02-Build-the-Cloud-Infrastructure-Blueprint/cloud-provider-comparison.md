# Cloud Provider Comparison

## Comparison Table

| Infrastructure Component | AWS | Microsoft Azure | Google Cloud Platform |
|---|---|---|---|
| Compute | EC2, Lambda, EKS | Virtual Machines, Azure Functions, AKS | Compute Engine, Cloud Functions, GKE |
| Storage | S3, EBS, EFS | Blob Storage, Managed Disks, Azure Files | Cloud Storage, Persistent Disk, Filestore |
| Networking | VPC, Route 53, CloudFront | VNet, Azure DNS, Azure Front Door | VPC (global by default), Cloud DNS, Cloud CDN |
| Identity and Access Management (IAM) | AWS IAM | Microsoft Entra ID (formerly Azure AD) | Google Cloud IAM |

## Guide Questions

### 1. Which cloud provider offers the broadest range of services? Explain your answer.
AWS offers the broadest range of services, with a catalog of well over 200 managed services compared to roughly 150–200 for Azure and GCP. Being the first major cloud provider, it has had the most time to build out specialized services for nearly every use case, and it has the largest ecosystem of third-party integrations, documentation, and community support to back it up.

### 2. Which cloud platform would you recommend for an organization that primarily uses Microsoft products?
Microsoft Azure is the clear recommendation. Its identity system, Microsoft Entra ID, provides native single sign-on across Office 365, Dynamics 365, and Active Directory, so an organization already standardized on Microsoft tools would face minimal friction adopting it. Azure's licensing and support relationships are also typically bundled with existing Microsoft enterprise agreements, making it the more cost-efficient and operationally simpler choice for that kind of organization.

### 3. Which platform is widely recognized for Artificial Intelligence (AI), Machine Learning (ML), and Kubernetes services?
Google Cloud Platform is the platform most closely associated with AI, ML, and Kubernetes. GCP created and open-sourced Kubernetes, so its managed offering (GKE) is generally considered the most refined implementation of it, and its AI/ML stack, including Vertex AI and custom-built TPU hardware, is a major differentiator, though AWS SageMaker and Azure Machine Learning remain strong, actively developed competitors in the same space.

### 4. What similarities did you observe among the three cloud providers?
All three providers are built around the same four core pillars: compute, storage, networking, and identity/access management, and their services map to each other almost one-to-one even though the names differ (for example, EC2, Azure VMs, and Compute Engine are functionally the same idea). All three also offer pay-as-you-go pricing with discounts for committed usage, managed Kubernetes services, and serverless compute options, which shows that despite competing on branding and pricing, the underlying architecture of "cloud computing" has converged into a shared set of expectations across the industry.
