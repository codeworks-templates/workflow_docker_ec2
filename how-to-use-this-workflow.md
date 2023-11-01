### Deploying Docker to EC2 🐳 ☁️

> To use this workflow you will need to add several [repository secrets](https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions)

To keep your environment variables safe during the build step you will need to create a DOCKER_COMPOSE secret which should be formatted as below.

_docker-compose.yml_
```yaml
version: '3'
services:
  app:
    image: your_dockerhub_username/your-repo-name:latest
    ports:
      - "7045:80"  # EC2_PORT:CONTAINER_PORT
    environment:
      - CONNECTION_STRING=
      - AUTH_DOMAIN=
      - AUTH_AUDIENCE=
      - AUTH_CLIENT_ID=
      - NODE_ENV=
```


This workflow is triggered when changes are made to the `production` branch
