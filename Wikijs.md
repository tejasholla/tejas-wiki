---
title: Wikijs
description: 
published: true
date: 2025-06-16T11:55:38.198Z
tags: server
editor: markdown
dateCreated: 2025-06-16T11:55:38.198Z
---

# wikijs
```docker
services:
 db:
   image: postgres:15-alpine
   container_name: wikijs-db
   environment:
     POSTGRES_DB: wiki
     POSTGRES_PASSWORD: wikijsrocks
     POSTGRES_USER: wikijs
   logging:
     driver: none
   restart: unless-stopped
   volumes:
     - /mnt/tank/configs/wikijs:/var/lib/postgresql/data
     - /home/wiki/github.pem:/home/node/.ssh/github.pem:ro
 wiki:
   image: ghcr.io/requarks/wiki:latest
   container_name: wikijs
   depends_on:
     - db
   environment:
     DB_TYPE: postgres
     DB_HOST: db
     DB_PORT: 5432
     DB_USER: wikijs
     DB_PASS: wikijsrocks
     DB_NAME: wiki
   restart: unless-stopped
   ports:
     - 3550:3000
```