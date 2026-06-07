# Installation

This guide explains how to install the Rux compiler.

---

## Windows

### Scoop (Recommended)

Add the Rux Scoop bucket:

```powershell
scoop bucket add rux-lang https://github.com/rux-lang/Scoop
```

Install Rux:

```powershell
scoop install rux-lang/rux
```

### Installer

Download the latest installer from the GitHub releases page.

Available installers:

* `.msi`
* `.exe`

Run the installer and follow the on-screen instructions.

---

## Arch Linux

Rux is available through the AUR.

```bash
yay -S rux-git
```

or

```bash
paru -S rux-git
```

---

## Fedora and COPR-based Distributions

Enable the Rux COPR repository:

```bash
sudo dnf copr enable zapaxe/Rux-Lang
```

Install Rux:

```bash
sudo dnf install rux
```

## Other Distributions

For distributions without an official package, Rux can be built from [source](https://github.com/rux-lang/Rux/).

See the build instructions in the repository for details.

---

## Verify Installation

Open a terminal and run:

```bash
rux version
```

Example output:

```text
Rux v0.3.0
```

The version number may differ depending on the installed release.

---

## Updating

### Scoop

```powershell
scoop update
scoop update rux
```

### Arch Linux

```bash
yay -Syu
```

### Fedora / COPR

```bash
sudo dnf upgrade
```
