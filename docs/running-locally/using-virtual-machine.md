# Using a virtual machine

Getting the app running locally isn't trivial, so this is a method that will setup a virtual machine on (pretty much) any machine!

There is still some things that need to be installed beforehand, but it is much less than [the alternative](./without-virtual-machine/getting-started.md).

## Setup

- 1 - [Install Virtual Box](https://www.virtualbox.org/wiki/Downloads)

- 2 - [Install Vagrant](https://www.vagrantup.com/downloads)

- 3 - [Install Python 3](https://www.python.org/downloads/)

> **NOTE:** its nice and easy to install Ansible using Pip, hence we ask to install Python.

- 4 - [Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-and-upgrading-ansible-with-pip)

> **NOTE:** There is multiple ways to install Ansible, but pip is the choice of this tutorial, hence we asked you to install Python 3.

- 5 - [Install GitHub Desktop](https://desktop.github.com/)

> **NOTE:** If you prefer to use `git` via the cli / some other tool to use GitHub, feel free to, but if you don't have a preference or are new to GitHub, I would recommend you install GitHub Desktop.

- 6 - [Clone Repository using GitHub Desktop](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/cloning-a-repository-from-github-to-github-desktop)

Head to [https://github.com/retrievium/retrievium](https://github.com/retrievium/retrievium) and follow the above instructions to clone the repository to your local machine.

If you can't access the above repo, you will need to reach out to someone to get your account added to the retrievium organization.

- 7 - Install Ansible Galaxy Requirements

Open up a terminal, and run the following command:

> On Linux, use a Terminal of your choice.
>
> On MacOS, use `Terminal`, it should be in the list of your existing programs.
>
> On Windows, use `cmd`.

```sh
cd /place/you/cloned/retrievium/iac-v1/ansible

ansible-galaxy install -r roles/requirements.yml
```

- 8 - Create virtual machine

_This one will likely take a while, but hopefully should require no interaction from you!_

```sh
cd /place/you/cloned/retrievium/iac-v1/vagrant/dev

vagrant up
```

- 9 - Run script to start tmux session

> **NOTE:** This command should be ran _inside_ your virtual machine, you can enter it by first heading into the `iac-v1/vagrant/dev` directory, and then running `vagrant ssh`
>
> ```sh
> cd /place/you/cloned/retrievium/iac-v1/vagrant/dev
vagrant ssh
> ```

```
# within VM
cd /vagrant/
make tmux
```

- 9 - Run script to add sample data

Once you have ran the above step, tmux should be running.

At the bottom of the screen you should see a green bar that starts with `[ret] 0:core 1:caddy...`, you can switch to the different panes by using `Ctrl + B + <NUMBER>`.

Use `Ctrl + B + 5` to head to the last pane (named terminal), and run:

```sh
cd /vagrant
make data
```

- Visit website in your browser!

Open up [http://localhost:2015/](http://localhost:2015/) in your web browser, the app _should_ be running, and also should have data!

> You can check this by visiting the search page, and just hitting search.
>
> There should be data returned.

## Tips

TODO tips about general usage
