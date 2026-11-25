# Update all containers

```
for service in $(docker compose config --services); do
    echo "===== Updating $service ====="
    docker compose pull "$service" && docker compose up -d "$service" || echo "FAILED: $service"
done
```