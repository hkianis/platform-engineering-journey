# Linux Development Environment Setup

## Purpose

This document records the Linux development environment used for the Platform Engineering Journey and the baseline validation performed before starting the Linux foundations labs.

The goal is to maintain a simple, reproducible environment suitable for Linux, container, Kubernetes, and infrastructure exercises.

## Environment

| Component | Configuration |
|---|---|
| Host OS | Windows |
| Linux environment | WSL2 |
| Distribution | Ubuntu 26.04 LTS |
| Architecture | x86_64 |
| Shell | Bash |
| Init system | systemd |
| Package manager | APT |
| Git | 2.53.0 |
| Repository location | `~/projects/platform-engineering-journey` |

The repository is intentionally stored inside the Linux filesystem rather than under `/mnt/c`.

## Baseline Validation

The following commands were used to inspect and validate the environment:

```bash
uname -a
cat /etc/os-release
whoami
id
echo $SHELL
pwd
df -h
free -h
ps -p 1 -o comm=
git --version
sudo -v
apt --version
sudo apt update
```

### Operating System

`/etc/os-release` confirmed:

```text
Ubuntu 26.04 LTS
```

The environment runs on the Microsoft WSL2 Linux kernel and uses the `x86_64` architecture.

### Shell and User Access

Bash is configured as the interactive shell.

The regular Linux user has access to `sudo`, which was validated successfully with:

```bash
sudo -v
```

Administrative commands can therefore be executed when required without operating permanently as the root user.

### systemd

The init process was inspected using:

```bash
ps -p 1 -o comm=
```

Result:

```text
systemd
```

This confirms that `systemd` is available in the WSL2 environment.

This is important for later labs involving:

- `systemctl`
- service lifecycle management
- `journalctl`
- service troubleshooting

### Package Management

APT is installed and functional.

Package repository metadata was refreshed successfully using:

```bash
sudo apt update
```

The configured Ubuntu repositories were reachable and the operation completed without repository errors.

No package upgrade was performed as part of this validation.

### Storage and Memory

The Linux root filesystem is separate from the Windows filesystem.

The Windows filesystem is mounted under:

```text
/mnt/c
```

Project files are kept under the Linux home filesystem:

```text
~/projects/
```

This avoids unnecessary dependency on Windows-mounted filesystem behavior during Linux labs.

CPU, memory, swap, and filesystem information can be inspected using:

```bash
free -h
df -h
```

The current environment has sufficient resources for the planned foundation labs.

## Git Repository Validation

The repository is located at:

```text
~/projects/platform-engineering-journey
```

Repository status was validated with:

```bash
git status
```

The repository was:

- on the `main` branch;
- synchronized with `origin/main`;
- using a clean working tree.

The remote configuration was inspected with:

```bash
git remote -v
```

The configured origin is:

```text
https://github.com/hkianis/platform-engineering-journey.git
```

Both fetch and push use the expected repository.

## Reproduction / Setup Procedure

From a fresh Ubuntu WSL2 environment, the project workspace can be prepared and validated with the following procedure:

```bash
mkdir -p ~/projects
cd ~/projects

git clone https://github.com/hkianis/platform-engineering-journey.git
cd platform-engineering-journey

sudo -v
sudo apt update
sudo apt install --dry-run curl

uname -a
cat /etc/os-release
whoami
id
echo $SHELL
pwd
df -h
free -h
ps -p 1 -o comm=

git --version
git fetch origin
git status
git remote -v
```

`apt install --dry-run curl` was used to validate package installation and dependency resolution without modifying the system.

In the current environment, `curl` was already installed, so APT planned an upgrade rather than a new installation.

## WSL2 Considerations

WSL2 provides a suitable environment for the current Linux foundation work, but it is not identical to a standalone Linux host.

For this project:

1. Linux labs should normally run inside WSL2.
2. Project files should remain inside the Linux filesystem where practical.
3. `/mnt/c` should not be used as the primary repository workspace.
4. WSL-specific behavior should be identified explicitly rather than assumed to represent all Linux environments.
5. A VM or native Linux host may be introduced later if a lab requires host behavior that WSL2 does not reproduce accurately.

## Validation Result

The development environment satisfies the baseline requirements for M1 Linux Foundations:

- [x] Working Linux shell
- [x] Ubuntu environment identified
- [x] Linux filesystem available
- [x] `systemd` available
- [x] `sudo` validated
- [x] APT validated
- [x] Git installed
- [x] Repository available inside the Linux filesystem
- [x] Repository synchronized with the expected GitHub remote

The environment is ready for the remaining M1 Linux labs.
