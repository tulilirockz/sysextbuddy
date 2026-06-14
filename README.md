# sysextbuddy

Sysext sysext bundler with reasonable defaults

This script generates systemd sysexts out of `/usr` or `/etc` trees, usually generated out of buildsystem artifacts like `meson compile`, you can then use this for i.e. persistently installing and testing your software built on top of a read-only `/usr` partition.

## Usage

```bash
# First generate your /usr tree first with whatever tool you want
sysextbuddy ./build/my-project --install # This will build and install your sysext to an ephemeral location
```
```
$ sysextbuddy ./build/brew-proxy/ --install
INFO: Sysext generated successfully at /var/home/tulip/opt/HastD/brew-proxy/brew-proxy.raw
Using extensions 'brew-proxy.raw'.
Unmerged '/usr'.
Merged extensions into '/usr'.
$ brew-proxy --help
Example usage:
  brew search TEXT|/REGEX/
  brew info [FORMULA|CASK...]
  brew install FORMULA|CASK...
  brew update
  brew upgrade [FORMULA|CASK...]
  brew uninstall FORMULA|CASK...
  brew list [FORMULA|CASK...]
...
```

## Inspirations

- <https://github.com/fedora-sysexts/fedora> - This is where I got most of the code, also SELinux support
- <https://gitlab.gnome.org/tchx84/sysext-utils> - Where the idea for this project came from!
