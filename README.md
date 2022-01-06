# azure-cli-community
AUR package for azure-cli isolated using virtualenv with symbolic linked to /usr/bin

The official install script for azure-cli from Microsoft fails when using Conda
to manage Python versions and environments. It then recommends to use a virtualenv
instead and use pip to install. While this works, azure-cli is only available when
the environment is currently active. To make in globally available, we could create
an alias.

Unfortunately, azure-identiy and azure-keyvault packages require azure-cli (az) to be
in /usr/bin. This can be solved by symbolically linking az to /usr/bin.

To simplify this process, I created these steps in a PKGBUILD.

## Build and install package

```bash
makepkg

sudo pacman -U azure-cli-community-2.XX.X-X.tar.zsg
```

