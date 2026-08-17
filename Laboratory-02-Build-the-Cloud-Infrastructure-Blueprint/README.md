# Laboratory 2: Build the Cloud Infrastructure Blueprint

## Mission Overview
This laboratory activity simulates the planning phase of a cloud deployment for CloudNova Technologies. A small company is preparing to migrate its services to the cloud, and before any servers are deployed, a Cloud Infrastructure Assessment Report is required. This activity involved inspecting a Linux server provisioned in the KillerCoda Playground, identifying its infrastructure components, comparing equivalent services across AWS, Microsoft Azure, and Google Cloud Platform, and designing a simple cloud architecture diagram.

## Objectives
- Explain the major components of cloud infrastructure.
- Investigate the hardware and software resources available in a Linux environment.
- Differentiate compute, storage, networking, and identity resources.
- Interpret the relationship between cloud infrastructure components.
- Create professional technical documentation using Markdown.
- Continue building a structured GitHub Cloud Computing Portfolio.

## Cloud Infrastructure Components
| Component | Description |
|---|---|
| Compute | A single vCPU (Intel Xeon E312xx) and 1.9Gi of RAM allocated to the KillerCoda instance, comparable to a minimal-tier cloud VM instance. |
| Storage | A 19G ext4 root volume plus separate boot and EFI partitions, comparable to a block storage volume attached to a cloud VM. |
| Networking | A primary interface IP (172.30.1.2) plus a Docker bridge IP (172.17.0.1), comparable to a private IP inside a cloud VPC/VNet. |
| Operating System | Ubuntu 24.04.4 LTS running kernel 6.8.0-136-generic, comparable to a machine image used to provision a cloud VM. |

## Tools Used
- KillerCoda Playground (Ubuntu 24.04 Linux environment)
- Linux command line utilities
- GitHub (version control and portfolio hosting)
- Draw.io (cloud architecture diagram)

## Linux Commands Executed
- cat /etc/os-release
- uname -r
- lscpu | grep "Model name"
- nproc
- free -h
- df -h
- mount | column -t
- hostname
- hostname -I

## Skills Learned
- Investigating a Linux system's hardware and software configuration entirely from the command line.
- Mapping the output of Linux system commands (CPU, RAM, disk, network) to real cloud infrastructure concepts like compute instances, block storage, and VPC networking.
- Comparing equivalent infrastructure services across AWS, Azure, and GCP using official documentation.
- Structuring technical documentation in Markdown with tables, headings, and consistent formatting.
- Managing a multi-file project through Git, including staged commits and structured folder organization.

## Challenges Encountered
- Interpreting less obvious command output, such as understanding why `hostname -I` returned two IP addresses (the primary interface plus a Docker bridge network) instead of just one.
- Deciding how to meaningfully relate a minimal sandboxed environment (1 vCPU, ~2GB RAM) to production-scale cloud infrastructure concepts.
- Keeping Markdown tables properly aligned and readable across multiple files.


