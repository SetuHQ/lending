minas-tirith

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
# Table of Contents

- [Table of Contents](#table-of-contents)
- [Getting started](#getting-started)
- [Developer Setup](#developer-setup)
  - [1. Fill in configuration in `docker-compose.yml`](#1-fill-in-configuration-in-docker-composeyml)
  - [2. Create a docker volume](#2-create-a-docker-volume)
  - [3. Bring up the setup](#3-bring-up-the-setup)
- [Production Deployment](#production-deployment)
  - [Using provided scripts](#using-provided-scripts)
  - [Other possibilities](#other-possibilities)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Getting started

To get started with minas-tirith, you'd need to install the following tools:

1. [Docker](https://docs.docker.com/get-docker/)
2. [Docker compose](https://docs.docker.com/compose/install/)

The setup consists of a postgresql database and a docker containerized service delivered by Setu.

# Developer Setup

To bring up a local developer setup,

## 1. Fill in configuration in `docker-compose.yml`

- Fill in the switch server credentials:

```bash
      # Switch server credentials
      - HTTP_PROXY=http://<user>:<password>@<switch-server>.setu.co:<port>
      - ALL_PROXY=http://<user>:<password>@<switch-server>.setu.co:<port>
```

- Fill in desired database credentials

```
      - POSTGRES_USER=minas-tirith
      - POSTGRES_PASSWORD=minas-tirith
      - POSTGRES_DB=minas-tirith
...
      - PGUSER=minas-tirith
      - PGPASSWORD=minas-tirith
      - PGDATABASE=minas-tirith
```

- Fill other credentials as communicated.

## 2. Create a docker volume

Create a docker volume to store the postgresql database

```bash
docker volume create --name=minas-tirith_db
```

## 3. Bring up the setup

```bash
docker-compose up
```

# Production Deployment

## Using provided scripts

TBD

## Other possibilities

TBD
