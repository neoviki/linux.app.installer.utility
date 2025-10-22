# Linux Application Installation Utility

**Linux Application Installation Utility** is a utility to install and uninstall multiple Linux/Mac applications or CLI tools from a configuration file. It supports Linux and Mac systems, the utility detects the host platform, and places the utilities in the appropriate binary directory.

This utility can be used as installer/uninstaller for **terminal-based applications, CLI tools, or Linux apps**. Developers can include this installer/uninstaller script alongside their applications to provide a **ready-to-use installation workflow** for end users.

---

## Features

* Install multiple CLI utilities or applications listed in a configuration file (`installation.config`).
* Auto detect **Linux** or **Mac** systems and installation to the appropriate directory (`/usr/local/bin` or `/usr/bin`).
* Sets executable permissions on installed files.
* Safe uninstallation with checks for missing files.
* Works with `sudo` if additional permissions are needed.
* Ideal for developers who want to provide a **ready-to-use installer/uninstaller** for their apps.

---

## Configuration File

The utility reads the list of utilities to install/uninstall from a config file:

```
installation.config
```

Example config file contents:

```
installer.sh
uninstaller.sh
```

> In this repository, we are using the installer and uninstaller themselves as example utilities. Developers can **replace these entries with their own applications or CLI tools**.

Each line should contain the **relative path** to a utility/application that needs to be installed.

---

## Installation

1. Clone the repository:

```bash
git clone <repo-url>
cd <repo-folder>
```

2. Make the installer executable:

```bash
chmod +x installer.sh
```

3. Run the installer:

```bash
./installer.sh
```

The utility will:

* Detect your system (Linux or Mac).
* Install each utility listed in `installation.config`.
* Print a **summary** showing which utilities were installed successfully or failed.

**Optional:** You can provide a custom configuration file:

```bash
./installer.sh my_apps.config
```

---

## Uninstallation

1. Make sure the uninstaller is executable:

```bash
chmod +x uninstaller.sh
```

2. Run the uninstaller:

```bash
./uninstaller.sh
```

The utility will:

* Remove each installed utility from the proper directory.
* Print a **summary** showing the removal status for each utility.

**Optional:** You can provide a custom configuration file:

```bash
./uninstaller.sh my_apps.config
```

---

## Usage Example

### Installer Output

```
[ status   ] Installing installer.sh to /usr/local/bin
[ success  ] installer.sh installed successfully
[ status   ] Installing uninstaller.sh to /usr/local/bin
[ success  ] uninstaller.sh installed successfully
==================== INSTALLATION SUMMARY ====================
 installer.sh                         : SUCCESS
 uninstaller.sh                       : SUCCESS
==============================================================
```

### Uninstaller Output

```
[ success  ] installer.sh removed successfully
[ success  ] uninstaller.sh removed successfully
==================== UNINSTALLATION SUMMARY ====================
 installer.sh                         : SUCCESS
 uninstaller.sh                       : SUCCESS
==============================================================
```

---

## Supported Systems

* Linux (Ubuntu, Debian, etc)
* MacOS

---

## Notes

* Make sure `installation.config` exists and points to the correct paths of your utilities.
* Use `sudo` if your install directory requires elevated permissions.
* The utility **does not overwrite existing files** without permission; check the directory if needed.
* Developers can **replace the example entries** in `installation.config` with their own applications or CLI tools to provide a ready-to-use installer/uninstaller for their software.

---

## License

[MIT License](LICENSE)

---
