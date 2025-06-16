---
title: papra
description: 
published: true
date: 2025-06-16T12:06:56.596Z
tags: server
editor: markdown
dateCreated: 2025-06-16T12:06:56.596Z
---

# papra
```
services:
  papra:
    container_name: papra
    restart: unless-stopped
    ports:
      - 1221:1221
    image: ghcr.io/papra-hq/papra:latest
networks: {}
```