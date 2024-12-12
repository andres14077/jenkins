
# Jenkins and SonarQube Setup

This repository contains the configuration to deploy Jenkins and SonarQube using Docker Compose.

## Requirements

- Docker
- Docker Compose

## Usage

1. Start the services:
    ```sh
    docker-compose up -d
    ```

2. Access Jenkins at `http://localhost:8080` and SonarQube at `http://localhost:9000`.

## Jenkins Configuration

The Jenkins container is configured to:

- Restart automatically (`restart: always`).
- Run in privileged mode.
- Expose ports 8080 and 50000.
- Mount volumes for data persistence and Docker socket access.

## SonarQube Configuration

The SonarQube container is configured to:

- Expose port 9000.
- Mount volumes for data persistence, extensions, and logs.

## Volumes

The volumes defined in `docker-compose.yml` ensure that Jenkins and SonarQube data persist between restarts:

- `jenkins_vol`: Jenkins data.
- `sonarqube_data`: SonarQube data.
- `sonarqube_extensions`: SonarQube extensions.
- `sonarqube_logs`: SonarQube logs.

