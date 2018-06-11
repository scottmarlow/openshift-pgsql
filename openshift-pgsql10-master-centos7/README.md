# OpenShift PostgreSQL Master

This project contains the PostgreSQL Master image for OpenShift.

## Getting Started

```bash
su -
systemctl start docker
make build
docker run -p 5432:5432 -e PG_DATABASE=mydb -e PG_USER_NAME=myuser -e PG_USER_PASSWORD=pass -e PG_REPLICATION_NAME=repl -e PG_REPLICATION_PASSWORD=replpass openshift-pgsql10-master-centos7
```

## Configuration

| Property | Default | Unit | Required | Description |
|----------|---------|------|----------|-------------|
| PG_DATABASE | | | Yes | The name of the database |
| PG_USER_NAME | | | Yes | The user name |
| PG_USER_PASSWORD | | | Yes | The password for the user |
| PG_REPLICATION_NAME | | | Yes | The replication user |
| PG_REPLICATION_PASSWORD | | | Yes | The password for the replication user |
| PG_DATABASE_ENCODING | UTF8 | | | The encoding of the database |
| PG_MAX_CONNECTIONS | 100 | | | `max_connections` setting |
| PG_SHARED_BUFFERS | 256 | MB | | `shared_buffers` setting |
| PG_WORK_MEM | 8 | MB | | `work_mem` setting |
| PG_MAX_PARALLEL_WORKERS | 8 | | | `max_parallel_workers` setting |
| PG_EFFECTIVE_CACHE_SIZE | 1 | GB | | `effective_cache_size` setting |