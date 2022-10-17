# Using a virtual machine

> **WARNING:** this method is easier than installing without a virtual machine, but if you are just starting out and planning to work on frontend tasks, follow [Just Frontend](./just-frontend.md) instead!

Getting the app running locally isn't trivial, so this is a method that will setup a virtual machine on (pretty much) any machine!

There is still some things that need to be installed beforehand, but it is much less than [the alternative](./without-virtual-machine/getting-started.md).

> **WARNING:** This setup does not currently support Apple M1 processors, due to Virtual Box not running on anything but x86, you will have to follow the other tutorial for now.

## Setup

- 1 - [Install Virtual Box](https://www.virtualbox.org/wiki/Downloads)

- 2 - [Install Vagrant](https://www.vagrantup.com/downloads)

- 3 - [Install GitHub Desktop](https://desktop.github.com/)

> **NOTE:** If you prefer to use `git` via the cli / some other tool to use GitHub, feel free to, but if you don't have a preference or are new to GitHub, I would recommend you install GitHub Desktop.

- 4 - [Clone Repository using GitHub Desktop](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/cloning-a-repository-from-github-to-github-desktop)

Head to [https://github.com/retrievium/retrievium](https://github.com/retrievium/retrievium) and follow the above instructions to clone the repository to your local machine.

If you can't access the above repo, you will need to reach out to someone to get your account added to the retrievium organization.

- 5 - Create virtual machine

_This one will likely take a while, but hopefully should require no interaction from you!_

```sh
cd /place/you/cloned/retrievium/iac-v1/vagrant/dev

vagrant up
```

If for some reason during this it fails, it might be due to a fluke of ansible, so you can run `vagrant provision` in the same directory again, and it will run the same scripts to download / setup all the software.

- 6 - Run script to start tmux session

> **NOTE:** This command should be ran _inside_ your virtual machine, you can enter it by first heading into the `iac-v1/vagrant/dev` directory, and then running `vagrant ssh`
>
> `cd /place/you/cloned/retrievium/iac-v1/vagrant/dev`
>
> `vagrant ssh`

```
# within VM
cd /vagrant/
make tmux
```

- 7 - Run script to add sample data

Once you have ran the above step, tmux should be running.

At the bottom of the screen you should see a green bar that starts with `[ret] 0:core 1:caddy...`, you can switch to the different panes by using `Ctrl + B + <NUMBER>`.

Use `Ctrl + B + 5` to head to the last pane (named terminal), and run:

```sh
cd /vagrant
make data
```

- 8 - Visit website in your browser!

Open up [http://localhost:2015/](http://localhost:2015/) in your web browser, the app _should_ be running, and also should have data!

> You can check this by visiting the search page, and just hitting search.
>
> There should be data returned.

- 9 - Verify you can make changes to the website, and the website will reflect them.

With your editor of choice, open up the repository. ([VSCode](https://code.visualstudio.com/) is a good choice if you don't have one already)

Head to `frontend-v1/src/components/particles_banner/ParticlesBanner.jsx`, and change the line:

```js
<Title style={{ fontWeight: "400", textAlign: "center" }}>
    retrievium
</Title>
```

To:

```js
<Title style={{ fontWeight: "400", textAlign: "center" }}>
    Hi, my name is YOUR_NAME
</Title>
```

After saving the file, the homepage of the website should automatically refresh with your changes.

## Tips

TODO tips about general usage

- shutting down the virtual machine
- disconnecting from tmux without shutting down the app
- attaching back to tmux again
- destroying the virtual machine
