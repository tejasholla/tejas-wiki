---
title: tianji
description: 
published: true
date: 2025-06-16T12:08:58.990Z
tags: server
editor: markdown
dateCreated: 2025-06-16T12:08:58.990Z
---

# tianji
```
services:
  tianji:
    image: moonrailgun/tianji:latest
    ports:
      - 12354:12345
    environment:
      DATABASE_URL: postgresql://tianji:tianji@postgres:5432/tianji
      JWT_SECRET: Klez17@ghost
      ALLOW_REGISTER: "false"
      ALLOW_OPENAPI: "false"
      OPENAI_API_KEY: random-string-of-characters
    depends_on:
      - postgres
    restart: always
  postgres:
    image: postgres:15.4-alpine
    environment:
      POSTGRES_DB: tianji
      POSTGRES_USER: tianji
      POSTGRES_PASSWORD: tianji
    volumes:
      - tianji-db-data:/var/lib/postgresql/data
    restart: always
    healthcheck:
      test:
        - CMD-SHELL
        - pg_isready -U $${POSTGRES_USER} -d $${POSTGRES_DB}
      interval: 5s
      timeout: 5s
      retries: 5
volumes:
  tianji-db-data: null
```