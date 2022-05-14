---
title: Run PostgreSQL via Docker
description: 
published: true
date: 2022-05-14T08:20:36.425Z
tags: 
editor: markdown
dateCreated: 2022-05-14T08:20:36.425Z
---

# Run Docker image for PostgreSQL

Make sure Docker is installed on your machine.

First we need to pull the PostgeSQL image:

```bash
docker pull postgres
```

Now we create and spin up the machine very easy:

```bash
docker run --name writeback-postgres-db \
  -e POSTGRES_DB="writeback_db" \
  -e POSTGRES_PASSWORD="<YourStrong@Passw0rd>" \
  -p 5432:5432 \
  -d postgres
```

**credentials**
user: postgres
password: <YourStrong@Passw0rd>

To check if its running, run the following "ps" command:

```bash
docker ps
```

Go to commandline postgres

```bash
docker exec -it writeback-postgres-db bash
```

```bash
psql -U postgres writeback_db
```

List all schemas

```psql
\dn
```

Use schema public in your env file

## References

- https://hub.docker.com/_/postgres
- https://towardsdatascience.com/local-development-set-up-of-postgresql-with-docker-c022632f13ea
