---
title: "Adicionando uma nova instância a um *cluster* do PostgreSql"
date: 2023-03-05T10:37:50-03:00
tags: [devops, postgresql, postgresql13, linux, debian, ubuntu]
draft: false
---

## Listar instâncias existentes no *cluster* do PostgreSQL

```bash
pg_lsclusters
```

```
Ver Cluster    Port Status Owner    Data directory                    Log file
13  main       5432 online postgres /var/lib/postgresql/13/main       /var/log/postgresql/postgresql-13-main.log
```
## Adicionar uma nova instância ao *cluster* do PostgreSQL

```bash
pg_createcluster 13 newinstancename
```
## Iniciar a nova instância do PostgreSQL

```bash
pg_ctlcluster 13 cbinstance start
```

## Alterar a senha do usuário `postgres`

```bash
sudo su - postgres
psql -p 5433
```

```
postgres=# \password
Type password:
Retype password:
```

