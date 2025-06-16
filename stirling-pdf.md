---
title: Stirling PDF
description: 
published: true
date: 2025-06-16T12:08:06.470Z
tags: server
editor: markdown
dateCreated: 2025-06-16T12:08:06.470Z
---

# Stirling PDF
```
version: "3.3"
services:
  stirling-pdf:
    image: docker.stirlingpdf.com/stirlingtools/stirling-pdf:latest
    ports:
      - 8180:8080
    volumes:
      - ./StirlingPDF/trainingData:/usr/share/tessdata # Required for extra OCR languages
      - ./StirlingPDF/extraConfigs:/configs
      - ./StirlingPDF/customFiles:/customFiles/
      - ./StirlingPDF/logs:/logs/
      - ./StirlingPDF/pipeline:/pipeline/
    environment:
      - DOCKER_ENABLE_SECURITY=false
      - LANGS=en_GB
```