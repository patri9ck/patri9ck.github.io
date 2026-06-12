[< Go Back](index.md)

# Server
The [A2LN server](https://github.com/patri9ck/a2ln-server) runs on your Linux computer and is responsible for receiving notifications and displaying them using _libnotify_.

## Installation
There are two ways to install the server.

### Package Manager
The easiest way to install the server is to use _pip_ or your system package manager. See [this issue](https://github.com/patri9ck/a2ln-server/issues/2) for the current status of packaging.

Distribution | Command | Note | Maintainer
------------ | ------- | ---- | ----------
[PyPI (pip)](https://pypi.org/project/a2ln/) | `python3 -m pip install a2ln` | No systemd user unit file | patri9ck
[Arch Linux / Manjaro (AUR)](https://aur.archlinux.org/packages/a2ln/) | `git clone https://aur.archlinux.org/a2ln.git && cd a2ln && makepkg -sirc` | | patri9ck

### Manually
First, clone the Git repository and check it out:
```
$ git clone https://github.com/patri9ck/a2ln-server.git
$ cd a2ln-server
```

#### Recommended: User Installation
For a user installation to `~/.local/bin`, run:
```
$ make install
```
Afterwards, if you have not already, add the following to your shell configuration file which will add the installation directory to `PATH`.
```
export PATH="${PATH}:${HOME}/.local/bin"
```

#### System Installation
Alternatively, do a system installation:
```
$ sudo make install
```

**Warning:** This will install all dependencies and can therefore result in broken permissions and conflicting behaviour with the system package manager. To avoid the installation of the dependencies, run this instead:
```
$ sudo make install FLAGS=--no-deps
```
This means that all dependencies must be installed by yourself, e.g. by using your system package manager.

## Setup
After installation, simply run the server like this:
```
$ a2ln
```
This will start the server on the default port which is 23045.

To get an overview of all command line options, use:
```
$ a2ln -h
```
### Autostarting
To automatically start the server at boot, the provided systemd user unit file can be used:
```
$ systemctl --user enable --now a2ln
```

Other options are:
- `~/.bash_profile`, `~/.zprofile`, ...
- `~/.xinitrc` or `~/.xprofile`
- Auto-start functions of your desktop environment or window manager

Also take a look at this [Arch Wiki article](https://wiki.archlinux.org/title/autostarting) about autostarting.
