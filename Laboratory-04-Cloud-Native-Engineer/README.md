# Laboratory 04 - Cloud-Native Engineer

## Mission Overview
In this lab, I stepped into the role of a Cloud-Native Engineer at CloudNova Technologies. The mission was to help a client understand why containers are a better fit for their web applications than traditional Virtual Machines. I used the KillerCoda Playground to run Docker commands, deployed a live Nginx web server inside a container, and documented the full lifecycle of that container — from pulling the image to removing it.

## Objectives
- Differentiate between traditional Virtual Machines (VMs) and Containers.
- Access a Docker-enabled cloud environment using KillerCoda.
- Execute fundamental Docker CLI (Command Line Interface) commands.
- Pull, run, manage, and terminate a containerized application (Nginx).
- Create professional technical documentation of container operations using Markdown.
- Continue developing a well-organized GitHub Cloud Computing Portfolio.

## Docker Commands Executed
| Command | Purpose |
|---|---|
| `docker --version` | Verify Docker is installed |
| `docker info` | Check current status of the Docker environment |
| `docker pull nginx` | Download the official Nginx image from Docker Hub |
| `docker run -d -p 8080:80 --name my-nginx nginx` | Run Nginx in detached mode, mapping host port 8080 to container port 80 |
| `curl http://localhost:8080` | Confirm the web server is responding |
| `docker ps` | List running containers |
| `docker stop my-nginx` | Stop the running container |
| `docker ps -a` | Verify the container has stopped |
| `docker rm my-nginx` | Remove the container completely |

## Skills Learned
- How to differentiate VMs from containers in terms of architecture, boot time, resource use, and isolation.
- How to verify a Docker environment and check its status.
- How to pull an image from Docker Hub and run it as a container.
- How port mapping (`-p`) connects a host port to a container's internal port.
- How to manage the full lifecycle of a container: list, stop, verify, and remove.
- How to document technical procedures clearly in Markdown for a non-technical audience (the client's IT team).

## Challenges Encountered
Initially ran into an issue where the KillerCoda session reset between checkpoints, which removed the running container before I could complete the lifecycle commands. This taught me that container state is tied to the session/host it runs on and doesn't persist automatically — I had to redo the deployment step and complete Checkpoints 4 and 5 together in one sitting.

## Screenshots
- `screenshots/docker-version.png` — Docker version and status check
- `screenshots/nginx-running.png` — Successful curl output from the running Nginx container
- `screenshots/container-lifecycle.png` — Container list, stop, verify, and remove sequence
