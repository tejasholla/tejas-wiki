---
title: arcane
description: 
published: true
date: 2025-06-17T05:59:21.480Z
tags: server, monitoring
editor: markdown
dateCreated: 2025-06-16T11:58:17.799Z
---

# arcane
```
services:
  arcane:
    image: ghcr.io/ofkm/arcane:latest
    container_name: arcane
    ports:
      - '3555:3000'
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - /mnt/tank/configs/arcane:/app/data
      - /mnt/tank/stacks:/app/data/stacks
    environment:
      - APP_ENV=production
      - PUID=568
      - PGID=568
      - PUBLIC_SESSION_SECRET=id
    restart: unless-stopped
```