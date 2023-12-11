[< Go Back](index.md)

# Server
The [A2LN server](https://github.com/patri9ck/a2ln-server) runs on your Linux computer and is responsible for receiving notifications and displaying them using _libnotify_.

## Installation
There are multiple ways to install the server.

Distribution | Command
------------ | -------
Manually*    | see below
[PyPI (pip)](https://pypi.org/project/a2ln/)* | `python -m pip install a2ln`
[Arch Linux / Manjaro (AUR)](https://aur.archlinux.org/packages/a2ln/) | `git clone https://aur.archlinux.org/a2ln.git && cd a2ln && makepkg -sirc`

*Does not install a systemd user unit file automatically. Also do not forget to add `$HOME/.local/bin` to `$PATH`.

### Manually
First, clone the Git repository and check it out:
```
$ git clone https://github.com/patri9ck/a2ln-server.git
$ cd a2ln-server
```

Afterwards, use _pip_ to install it:
```
$ python -m pip install .
```

To uninstall, use:
```
$ python -m pip uninstall a2ln
```

## Usage
After installation, simply run the notification server like this:
```
$ a2ln
```

To pair a new phone, use:
```
$ a2ln pair
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
$ systemctl --user enable --now a2ln
```

Other options are:
- `~/.bash_profile`, `~/.zprofile`, ...
- `~/.xinitrc` or `~/.xprofile`
- Auto-start functions of your desktop environment or window manager

Also take a look at this [Arch Wiki article](https://wiki.archlinux.org/title/autostarting) about autostarting.
