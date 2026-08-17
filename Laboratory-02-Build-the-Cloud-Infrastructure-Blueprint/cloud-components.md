# Cloud Infrastructure Components

## 1. Compute Resources
Purpose: Compute resources provide the processing power (CPU and memory) needed to run applications, services, and operating system processes.

Why it matters in cloud computing: Compute is the foundation every other cloud service runs on top of. Providers let customers provision compute on demand and scale it up or down instead of buying physical servers.

In the KillerCoda environment: The Playground itself is a compute resource — a virtual instance running Ubuntu 24.04 with a single Intel Xeon E312xx (Sandy Bridge) CPU core allocated (confirmed via nproc and lscpu), plus 1.9Gi of RAM (confirmed via free -h). This mirrors how a cloud provider allocates a specific vCPU and memory size to a virtual machine instance, such as an AWS EC2 t3.micro or similar minimal-tier instance.

## 2. Storage Resources
Purpose: Storage resources hold data — OS files, application data, logs, and user files — temporarily or persistently.

Why it matters in cloud computing: Cloud storage needs to be durable, scalable, and often decoupled from compute so data persists even if the compute instance is replaced.

In the KillerCoda environment: df -h showed a 19G root disk (/dev/vda1, ext4) with 5.4G used and 13G available, plus a separate /boot (/dev/vda16, ext4) and /boot/efi (/dev/vda15, vfat) partition. This mirrors how a cloud VM attaches a root block volume (similar to an AWS EBS volume or Azure Managed Disk) with a defined capacity that persists independently of the compute instance itself.

## 3. Networking Resources
Purpose: Networking resources connect compute and storage to each other and to the outside world — IP addressing, routing, and interfaces.

Why it matters in cloud computing: Without networking, isolated compute and storage would be unreachable and useless. Networking also defines security boundaries and how services communicate.

In the KillerCoda environment: hostname -I returned two addresses — 172.30.1.2, the primary interface address used to reach this instance, and 172.17.0.1, which is a Docker bridge network address running underneath the Playground. This models the same layered networking found in real cloud environments, where a VM has a primary private IP inside a VPC/VNet, and container workloads on top of it get their own internal bridge network (similar to how AWS ECS or a self-managed Docker host on EC2 behaves).

## 4. Operating System
Purpose: The OS manages hardware resources and provides the platform applications run on — process scheduling, memory management, filesystem access, and networking.

Why it matters in cloud computing: Cloud compute instances are provisioned from machine images that bundle a specific OS and kernel version, which affects compatibility, security patching, and available tooling.

In the KillerCoda environment: cat /etc/os-release confirmed the instance runs Ubuntu 24.04.4 LTS (Noble Numbat) on kernel 6.8.0-136-generic. This is the same information a cloud engineer checks when selecting or auditing a machine image, such as an AWS AMI, Azure VM image, or GCP Compute Engine image, to confirm what OS and patch level a fleet of instances is running.

## Summary Table
| Component | KillerCoda Evidence | Cloud Equivalent Concept |
|---|---|---|
| Compute | 1 vCPU (Intel Xeon E312xx), 1.9Gi RAM | EC2 / Azure VM / Compute Engine instance |
| Storage | 19G ext4 root volume, separate boot partitions | EBS / Managed Disk / Persistent Disk |
| Networking | Primary IP 172.30.1.2 + Docker bridge 172.17.0.1 | VPC/VNet IP addressing + container networking |
| Operating System | Ubuntu 24.04.4 LTS, kernel 6.8.0-136-generic | Machine Image (AMI / VM Image / GCE Image) |
