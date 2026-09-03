# Virtualization & Linux

## Objective

The goal of this milestone is to create the first Linux server of the homelab.

## Host System

- Device: MacBook Air M4
- Architecture: ARM64 / Apple Silicon
- Memory: 16 GB
- Host OS: macOS

## Virtualization Platform

### UTM

UTM was selected as the virtualization platform for this lab.

It supports Apple Silicon and allows us to run ARM64 virtual machines using Apple's virtualization framework.

## First Virtual Machine

| Setting | Configuration |
|---|---|
| Hostname | `ubuntu-server-01` |
| OS | Ubuntu Server 24.04 LTS |
| Architecture | ARM64 |
| CPU | 2 cores |
| RAM | 2 GB |
| Disk | 25 GB |
| Network | Shared Network |
| SSH | OpenSSH Server |
| Virtualization | Apple Virtualization |

## Networking

The virtual machine received its network configuration through DHCP.

- Interface: `enp0s1`
- IPv4: `192.168.64.2/24`

## Remote Administration

OpenSSH Server was installed during the Ubuntu installation.

The connection was successfully tested from macOS:

```bash
ssh melina@192.168.64.2
```

This allows the Ubuntu server to be administered remotely from the macOS Terminal instead of relying exclusively on the UTM console.

## Initial System Setup

After installation, the package information and installed packages were updated using:

```bash
sudo apt update
sudo apt upgrade
```

The server was also verified using commands such as:

`whoami`
`hostname`
`ip addr`
`uname -a`
`lsb_release -a`
`df -h`
`free -h`

## Result

The first Linux server of the homelab is now operational and accessible remotely through SSH.
This server will be used to practice:

- Linux administration
- Users and groups
- File permissions
- Networking
- SSH
- Services
- Logging
- Automation
- System hardening
- Security monitoring
