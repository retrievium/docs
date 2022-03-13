# openapi-v1

OpenAPI Documentation for api-v1.

## TODOs

1. Proper status codes for everything!
2. Location and timestamp property in responses
3. Better pagination

## Setup

```sh
cd openapi-v1
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

## Viewing the documentation

Requirements:

- Running Caddy with `local`

```sh
npm run serve
```

The OpenAPI docs _should_ now be available behind Caddy at [http://localhost:2015/openapi/v1/](http://localhost:2015/openapi/v1/).

## Building the documentation

```sh
npm run build
```
