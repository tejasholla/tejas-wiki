---
title: anirra
description: 
published: true
date: 2025-06-16T11:59:09.133Z
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
      - NEXTAUTH_URL=https://anime.techfiles.in
    volumes:
      - ./data:/project/data
      - ./config.yaml:/project/config.yaml
    ports:
      - 3120:3000
      - 8120:8000
```