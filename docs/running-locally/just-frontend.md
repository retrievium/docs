# Just the frontend

There are two methods to run the entire app, either [without a virtual machine](./without-virtual-machine/getting-started.md), or by running in a [virtual machine](./using-virtual-machine.md).

Both have their own issues sadly and are not trivial if you haven't been exposed to application development much before.

So, the third and easiest route to get the app running locally is to _just_ run the frontend, and use Caddy as a reverse proxy.

## Setup

- 1 - [Install GitHub Desktop](https://desktop.github.com/)

> **NOTE:** If you prefer to use `git` via the cli / some other tool to use GitHub, feel free to, but if you don't have a preference or are new to GitHub, I would recommend you install GitHub Desktop.

- 2 - [Clone Repository using GitHub Desktop](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/cloning-a-repository-from-github-to-github-desktop)

Head to [https://github.com/retrievium/retrievium](https://github.com/retrievium/retrievium) and follow the above instructions to clone the repository to your local machine.

If you can't access the above repo, you will need to reach out to someone to get your account added to the retrievium organization.

- 3 - Download Caddy

Linux:

```sh
cd /place/you/cloned/retrievium/ops-v1/caddy

./download_caddy.sh
```

Windows:

```bat
TODO
```
