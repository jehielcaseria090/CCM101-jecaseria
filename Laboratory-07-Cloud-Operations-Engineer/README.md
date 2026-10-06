# Laboratory 07: The Cloud Operations Engineer

## Mission Overview

CloudNova Technologies is preparing for a large marketing campaign, and the client is worried the servers will run out of memory when thousands of users visit. In this mission I acted as a Cloud Operations Engineer. I established a baseline for the host server, deployed an Nginx container, generated normal and failing web traffic, and used logs and live metrics to show the infrastructure is healthy.

## Objectives

- Use native Linux tools to monitor host CPU, memory, and disk capacity.
- Deploy a web container and track its real-time performance with Docker metrics.
- Generate web traffic and extract application access logs for analysis.
- Turn raw performance data into a readable technical report using Markdown.
- Continue building a professional GitHub Cloud Computing Portfolio.

## Monitoring Commands Executed

- `free -h`: checked total, used, and available RAM (1.9 GiB total).
- `df -h`: checked disk capacity of the root (/) file system.
- `top`: viewed running processes and live CPU load.
- `docker run -d --name client-website -p 8080:80 nginx`: deployed the Nginx web server in the background.
- `curl http://localhost:8080`: sent three successful requests (HTTP 200).
- `curl http://localhost:8080/hidden-admin-page`: triggered an HTTP 404 error.
- `docker logs client-website`: retrieved the application access and error logs.
- `docker logs client-website 2>&1 | grep '" 404 '`: isolated the 404 log line.
- `docker stats`: viewed live CPU, memory, and network usage (2.738 MiB memory, 0.00% CPU).

## Skills Learned

- Establishing a host performance baseline with standard Linux CLI tools.
- Running and naming a container, and mapping a host port to it.
- Simulating user traffic and deliberately triggering HTTP errors.
- Reading and filtering application logs to find specific status codes.
- Interpreting real-time container metrics for CPU, memory, and network I/O.
- Documenting system health in Markdown and managing work with Git and GitHub.
