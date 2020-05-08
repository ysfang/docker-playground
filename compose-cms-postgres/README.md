# Docker Compose for Drupal and Postgres

## Introduction

Practice for Docker Compose, a Drupal CMS web and a Postgres DB.

## Detail

* Create named volumes for services. Add different appraoches to use volumes in comment areas.
* Create bridge (default) network for the services. Can uncomment ports setting for debugging externally.

## Usage

```bash
// run the CMS and DB
docker-compose up

// tear down
docker-compose down

```
