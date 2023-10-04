# Docker Image Redis

- Here's the file image field in docker-compose.yml
```bash
  version: '3.8'  # You can use a different version if you prefer
  services:
    redis:
      build: 
        context: ./docker/redis
      volumes:
        - ./docker/redis/redis.conf:/etc/redis/redis.conf
      ports:
        - "6370:6379"
      environment:
        - REDIS_PASSWORD=redis123
      command: /bin/sh -c "redis-server --requirepass $$REDIS_PASSWORD"
```

- You can build and run your Docker container using the following commands:
```bash
  docker-compose up --build
```
