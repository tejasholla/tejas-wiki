---
title: anirra
description: 
published: true
date: 2025-06-17T05:59:44.963Z
tags: server
editor: markdown
dateCreated: 2025-06-16T11:59:09.133Z
---

# anirra
```
services:
  anirra:
    container_name: anirra
    image: jpyles0524/anirra:latest
    build:
      context: .
      dockerfile: Dockerfile
    command: bash /start.sh
    environment:
      - APP_LEVEL=PROD
      - NEXTAUTH_URL=url
    volumes:
      - ./data:/project/data
      - ./config.yaml:/project/config.yaml
    ports:
      - 3120:3000
      - 8120:8000
```