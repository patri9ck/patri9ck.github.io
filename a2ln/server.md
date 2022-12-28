[< Go Back](index.md)

# Server
The [A2LN server](https://github.com/patri9ck/a2ln-server) runs on your Linux computer and is responsible for receiving notifications and displaying them using _libnotify_.

## Installation
The easiest way to install the server is to use your package manager. See [this issue](https://github.com/patri9ck/a2ln-server/issues/2) for the current status of packaging.

Distribution | Maintainer
------------ | ----------
[Arch Linux / Manjaro (AUR)](https://aur.archlinux.org/packages/a2ln/) | patri9ck

Alternatively, you can install it manually:
```
$ git clone https://github.com/patri9ck/a2ln-server.git
$ cd a2ln-server
$ sudo make install
```
Make sure there is Python 3.8 or newer set up on your system.

You will probably need to install all required runtime dependencies as well, either by using your package manager or by running:
```
$ python -m pip install -r requirements.txt
```

To uninstall it, run:
```
$ sudo make uninstall
```

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
