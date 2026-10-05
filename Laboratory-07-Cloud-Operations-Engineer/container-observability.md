# Container Observability

## 404 Log Entry

```
172.17.0.1 - - [05/Oct/2026:23:52:41 +0000] "GET /hidden-admin-page HTTP/1.1" 404 153 "-" "curl/8.5.0" "-"
```

## Why Application Logs Matter

Application logs record every request and error with a timestamp, so an engineer can see exactly what happened and when something broke. Without them, troubleshooting is guesswork, because they show the failing URL, the status code, and the client that triggered it.

## Container Metrics (docker stats)

- **Container:** client-website
- **Memory Usage:** 2.738MiB / 1.859GiB (0.14%)
- **CPU Usage:** 0.00%
