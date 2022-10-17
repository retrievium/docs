# Running frontend-v1 locally

React frontend to interface with api-v1.

## Setup

```sh
cd frontend-v1
```

### Required dependencies

_Note: api-v1 asks you to install these things, if you have already done this you should be good to skip installing again_.

- [Node 17+](https://nodejs.org/en/)
- [Node Version Manager](https://github.com/nvm-sh/nvm)

You should use Node Version Manager to install Node, such that you can get the most recent stable version of it.

### Install projects Node version, and install the required NPM packages

```sh
nvm use
npm i
```

### Initialize secrets

```sh
cp .env.dist .env
```

## Running the frontend

Requirements:

- Running Caddy with `dev` as in [`ops-v1`](./ops-v1.md)

```sh
npm run start
```

Note: create-react-app will stat listening on localhost:3000, but DO NOT use this to view the page, since it will fail making API requests due to CORS.

The frontend should now be served by Caddy at [http://localhost:2015/](http://localhost:2015/)

### Building the frontend

```sh
npm run build
```
