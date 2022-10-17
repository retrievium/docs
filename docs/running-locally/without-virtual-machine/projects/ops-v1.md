# Running ops-v1 locally

Ops contains files required to run all of the services that the projects used that we don't develop ourselves.

## Setup

```sh
cd ops-v1
```

### Required dependencies

- [Docker](https://docs.docker.com/install/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Caddy](https://github.com/caddyserver/caddy)

#### Installing Caddy

```sh
cd caddy
sh download_caddy.sh # downloads caddy via webinstall.dev
```

If you are running production and wish Caddy to be able to bind on ports 80 / 443, run the following script:

```sh
sh allow_caddy_bind.sh 
```

It will (should) allow caddy to listen on ports below 1024 without sudo

### Populating secrets

Before the first run, the secrets folder must be populated.

```sh
cd core
sh create_secrets.sh
```

### Populating Docker images / volumes

Before the first run, Docker expects certain volumes to be created externally.

```sh
cd core
sh create_volumes.sh
```

## Running core services in development

### Running Caddy

```sh
cd caddy
sh start_caddy.sh dev  # run caddy, expecting to run on localhost on port 2015
```

### Running core services

```sh
cd core
docker-compose up -d
```

## Potential issues

### ElasticSearch memory error

Elasticsearch seems to bail before starting in Linux due to something relating [this issue](https://www.elastic.co/guide/en/elasticsearch/reference/current/vm-max-map-count.html).

Thankfully the fix is easy, and contained within this repository for ease-of-access.

```sh
cd core
sh es_mem_fix.sh
```

