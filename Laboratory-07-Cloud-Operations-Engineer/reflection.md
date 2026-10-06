# Mission Reflection

Checking the host server's resources matters even when my containers run perfectly, because every container shares the host's CPU, memory, and disk. My host had only about 1.9 GiB of RAM, so a traffic surge could exhaust memory or fill the disk and take down every container at once. The host is the foundation, and a problem there affects everything running on top of it.

If a user could not log in, docker logs would show me the requests that reached the application and their status codes, such as 200, 401, or 500. Error lines like the 404 I generated for /hidden-admin-page reveal the exact URL, time, and client, so I can pinpoint the cause instead of guessing.

Logs and metrics answer different questions. Logs are records of events that tell me what happened, such as which request failed and when. Metrics are numbers measured over time, such as the 0.00% CPU and 2.738 MiB memory in docker stats, which tell me how loaded the system is. Logs help me diagnose a specific failure, while metrics help me spot trends and warn me before something breaks.

Large enterprises cannot run docker stats by hand on thousands of containers. They use Prometheus to collect metrics automatically from every container and Grafana to show them on dashboards with alerts, often alongside central log collection and orchestrators like Kubernetes. This lets a small team watch a huge infrastructure and get notified when a threshold is crossed.

My Linux troubleshooting has improved because I now know which tool to reach for first: free -h and df -h for capacity, top for processes, docker logs for events, and docker stats for resource use. I also learned to filter output with grep and to read results carefully, since I caught a wrong screenshot and a broken file along the way. I now approach problems with evidence instead of assumptions.
