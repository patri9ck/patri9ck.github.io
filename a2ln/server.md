[< Main page](index.md)

The [A2LN server](https://github.com/patri9ck/a2ln-server) runs on your Linux computer and is responsible for receiving notifications and displaying them using _libnotify_.

# Installation
The easiest way to install the server is to use your package manager. See [this issue](https://github.com/patri9ck/a2ln-server/issues/2) for the current status of packaging.

Distribution | Maintainer
------------ | ----------
[Arch Linux / Manjaro (AUR)](https://aur.archlinux.org/packages/a2ln/) | patri9ck

Alternatively, you can install it manually:
```
$ git clone https://github.com/patri9ck/a2ln-server.git
$ cd a2ln-server
# make install
```
Another way is to save the `a2ln` script directly from the GitHub repository somewhere under your home directory and then to run it from there.

All required runtime dependencies are listed [here](https://github.com/patri9ck/a2ln-server/blob/main/requirements.txt).

# Setup
After installation, you can run the server like this:
```
$ a2ln <PORT>
```
Replace `<PORT>` with the port you want to use. **You must use a port higher than 1023 if you are not root.**

You probably want to auto-start it. Common options to do so are:
- `~/.bash_profile`, `~/.zprofile`, ...
- `~/.xinitrc` or `~/.xprofile`
- Systemd user units
- Auto-start functions of your desktop environment or window manager

Also take a look at this [Arch Wiki article](https://wiki.archlinux.org/title/autostarting) about auto-starting.
