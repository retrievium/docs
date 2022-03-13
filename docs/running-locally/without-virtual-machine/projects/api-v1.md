# Running api-v1 locally

API for accessing the retrievium data.

The frontend will talk to this API to access data, nothing outside of the backend should ever talk directly to the databases, the API is the layer that abstracts them.

## Setup

```sh
cd api-v1
```

### Required dependencies

- [Node 17+](https://nodejs.org/en/)
- [Node Version Manager](https://github.com/nvm-sh/nvm)

You should use Node Version Manager to install Node, such that you can get the most recent stable version of it.

### Install projects Node version, and install the required NPM packages

```sh
nvm use
npm install
```

## Populate the ElasticSearch CML index

**IMPORTANT:** assuming you have already setup ElasticSearch, explained in `ops-v1`, run the following command after you have done the above to generate the index ElasticSearch will use to store CML files.

```sh
npm run elasticsearch:generate-index
```

## Running the api

Requirements:

- Running all core services (Caddy and the required docker containers noted in [`ops-v1`](./ops-v1.md))

```sh
nvm use
npm start
```

The API _should_ now be running behind Caddy at [http://localhost:2015/api/v1/](http://localhost:2015/api/v1/).
