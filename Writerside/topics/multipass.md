# Multipass

**Multipass** is a lightweight VM manager for Linux, Windows, and macOS.
You are recommended to use it, if you use macOS.

## Installation

### Installer

One way to install Multipass is to use the installer.

Visit [Multipass Install](https://multipass.run/install) and download the **pkg** file.

### Homebrew

You can also use **Homebrew** to install Multipass.

```Shell
brew install multipass
```

## Usage

To use Multipass, you need to first create an instance.

```Shell
multipass launch -n primary
```

This will create a new instance named `primary`.

To use its shell, you can run:

```Shell
multipass shell primary
```

## Network

By default, Multipass has no network connection, when you use a VPN.

To solve this, run `ifconfig` in the shell, and find the name of the network interface. \
For example, it may be `utun4`.

![ifconfig.png](ifconfig.png)

Then write the following (replace `utun` with yours) to `/etc/pf.conf`:

```Shell
nat on utuen4 from bridge100:network to any -> (utun4)
```

And run:

```Shell
sudo pfctl -f /etc/pf.conf
```

This will allow Multipass to use the VPN connection.