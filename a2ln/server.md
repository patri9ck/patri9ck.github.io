[< Go Back](index.md)

# Server
The [A2LN server](https://github.com/patri9ck/a2ln-server) runs on your Linux computer and is responsible for receiving notifications and displaying them using _libnotify_.

## Installation
There are two ways to install the server.

### Package Manager
The easiest way to install the server is to use _pip_ or your system package manager. See [this issue](https://github.com/patri9ck/a2ln-server/issues/2) for the current status of packaging.

Distribution | Command | Note
------------ | ------- | ----
[PyPI (pip)](https://pypi.org/project/a2ln/) | `python -m pip install a2ln` | No systemd user unit file
[Arch Linux / Manjaro (AUR)](https://aur.archlinux.org/packages/a2ln/) | `git clone https://aur.archlinux.org/a2ln.git && cd a2ln && makepkg -sirc`

### Manually
First, clone the Git repository and check it out:
```
$ git clone https://github.com/patri9ck/a2ln-server.git
$ cd a2ln-server
```

Afterwards, use _make_ to build and install it:
```
$ make
# make install
```

Do not forget to install all [dependencies](https://github.com/patri9ck/a2ln-server/blob/main/requirements.txt), preferrably using your package manager.

To uninstall, use:
```
# make uninstall
```

## Usage
After installation, simply run the notification server like this:
```
$ a2ln
```

To pair a new phone, use:
```
$ a2ln pairing
```

To get an overview of all command line options, execute:
```
$ a2ln -h
```

### Toggling Notifications
To toggle whether notifications are shown or not, a `SIGUSR1` signal can be sent:
```
$ killall -SIGUSR1 a2ln
```

## Autostarting
To automatically start the server at boot, the provided systemd user unit file can be used:
```
# systemctl enable --now a2ln
```

Other options are:
- `~/.bash_profile`, `~/.zprofile`, ...
- `~/.xinitrc` or `~/.xprofile`
- Auto-start functions of your desktop environment or window manager

Also take a look at this [Arch Wiki article](https://wiki.archlinux.org/title/autostarting) about autostarting.
