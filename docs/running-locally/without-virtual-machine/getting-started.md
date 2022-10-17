# Getting started

> **WARNING:** a lot of work has been put into making ['Using a Virtual Machine'](../using-virtual-machine.md) the best way get the entire app running on any machine as fast as possible.
>
> while you are welcome to follow the bellow instructions, you should probably at least try the other method first!

The goal of this section is to take you from nothing, to entire app running.

## Environment

The install process will reference Unix commands you should run within code blocks, therefore it is expected that you are running such an environment.

If you are:

1. Running Linux, you are fine.
2. Running MacOS, you are _likely_ fine, but there might be some differences here and there with how things operate.
3. Running Windows, you should likely check out the [WSL](./wsl.md) section here beforehand, so you can spin up a Linux-like environment within Windows beforehand.

_If you run into a problem with something here, and find the solution, please contribute it back to the documentation to help those in the future!_

## Overview of steps

- [Clone the repository:](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)

```sh
git clone git@github.com:retrievium/retrievium.git
cd retrievium
```

- Copy `.env.dist` to `.env` in the root folder of the project.

```
cp .env.dist .env
```

- [Follow the instructions in `ops-v1` to sort out Docker / Caddy / Databases / etc](./projects/ops-v1.md).

> You should have Minio, ElasticSearch, Faktory, and Postgres running, along with Caddy before proceeding to the next step.

- [Follow the instructions in `api-v1` to setup the backend API](./projects/api-v1.md).

> You should be able to run the API before proceeding to the next step, as well as ran the script to populate the ElasticSearch indexes.

- [Follow the instructions in `gulper-v1` to setup the ingestion pipeline / worker](./projects/gulper-v1.md).

> You should have data in your database after this step, which means you have uploaded the sample tar, ran the worker, and had the worker process said sample tar into Minio / ElasticSearch / Postgres.

- [Follow the instructions in `frontend-v1` to setup the frontend](./projects/frontend-v1.md)

> You should be running the development build of the React application before proceeding to the next step.

- Visit [http://localhost:2015/](http://localhost:2015) in your browser, everything _should_ be running!

## Troubleshooting

If you made it to the last step, but you don't see the homepage, double check if you are:

- Running all of the required docker containers noted in [`ops-v1`](./projects/ops-v1.md), along with Caddy too.
- Have populated the databases with sample data.
- Running the API.
- Running the frontend.

If that isn't the case / you have gotten stuck part way through, feel free to reach out in the Retrievium Discord server, for (hopefully) assistance from previous developers.

If you are not in this discord server, reach out to the professors for access.
