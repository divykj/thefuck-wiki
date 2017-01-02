# Generic way

You need to install requirements:
- pip
- python
- python-dev (or python-devel on some distros: Fedora, CentOS)

And then install `thefuck` with `pip`:

```bash
sudo -H pip install thefuck
```

# OS X

```bash
brew install thefuck
```

or

```bash
sudo easy_install thefuck
```

# Ubuntu

:exclamation: Do not use `sudo easy_install pip`, it does not work on Ubuntu.

```bash
sudo apt-get install python-pip python-dev
sudo pip install psutil thefuck
```

# Arch

```bash
sudo pacman -S thefuck
```

# Fedora

```bash
sudo dnf install python-pip python-devel
sudo pip install thefuck
```

# Gentoo

```bash
sudo emerge --ask app-shells/thefuck
```

# Void Linux
```bash
sudo xbps-install thefuck
```