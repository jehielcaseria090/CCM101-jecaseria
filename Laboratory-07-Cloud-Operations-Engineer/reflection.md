# Mission Reflection

Checking the host server is important even when my containers run fine, because all containers share the same CPU, memory, and disk of the host. My server has only about 1.9 GiB of RAM. If many users visit at once, the memory or disk can get full and all the containers can stop. The host is the base, so if it has a problem, everything on top of it has a problem too.

If a user cannot log in, I would run docker logs to see the requests that reached the app and their status codes, like 200, 401, or 500. An error line, like the 404 I made for /hidden-admin-page, shows the exact page, the time, and who sent the request. This helps me find the real cause and not just guess.

Logs and metrics answer different questions. Logs are records of events. They tell me what happened, like which request failed and when. Metrics are numbers that show how hard the system is working, like the 0.00% CPU and 2.738 MiB memory in docker stats. Logs help me find the cause of a problem. Metrics help me see changes early, before something breaks.

Big companies cannot run docker stats by hand on thousands of containers. They use Prometheus to collect numbers from all the containers automatically, and Grafana to show them on dashboards with alerts. They also use tools like Kubernetes to manage the containers. This way, a small team can watch a large system and get a message when something goes wrong.

My Linux troubleshooting is better now because I know which tool to use first: free -h and df -h for space, top for processes, docker logs for events, and docker stats for resource use. I also learned to use grep to find one line in a long output. Now I solve problems with proof, not guesses.
