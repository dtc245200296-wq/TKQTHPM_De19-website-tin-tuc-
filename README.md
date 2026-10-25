**Website Tin tức / Cổng thông tin (WordPress) triển khai bằng Docker Compose.**

## Services
WordPress, MySQL, phpMyAdmin, Nginx, Prometheus, Grafana, Loki, Promtail, cAdvisor, Node Exporter.

## Start
1. Configure .env using .env.example and set strong passwords.
2. Validate: docker compose config --quiet
3. Start: docker compose up -d

## Local URLs
- News Portal via Nginx: http://localhost:80
- phpMyAdmin: http://localhost:8080
- Prometheus: http://localhost:9090
- Grafana: http://localhost:3000

## LogQL examples
{job="nginx"}
{job="nginx"} | regexp "(?P<level>info|warn|error|Deactivated|Started)"
{job="nginx"} |~ "(?i)error|deactivated|failed"

Never commit .env or real credentials.
