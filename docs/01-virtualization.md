01 - Virtualization & Linux

Objective

Create the first Linux server of the homelab and establish a foundation for system administration, networking, remote access, and later security exercises.

Host System

Device: MacBook Air M4

Architecture: ARM64 / Apple Silicon

Memory: 16 GB

Host OS: macOS

Because the host uses ARM64 architecture, the virtual machines should use ARM64 operating systems whenever possible instead of relying on x86_64 emulation.

Virtualization Platform

UTM

UTM was selected as the virtualization platform for this lab.

It supports Apple Silicon and can use Apple's virtualization framework to run ARM64 virtual machines efficiently.

For this lab, native ARM64 virtualization is preferred over full x86_64 emulation because it provides better performance and lower resource usage.

First Virtual Machine

The first server deployed in the lab is:

Hostname: ubuntu-server-01

Operating System: Ubuntu Server 24.04 LTS

Architecture: ARM64

CPU: 2 cores

RAM: 2 GB

Virtual Disk: 25 GB

Network Mode: Shared Network

Virtualization: Apple Virtualization

Rosetta: Enabled for optional x86_64 compatibility

OpenGL Acceleration: Disabled

Shared Directory: Disabled

Ubuntu Server was chosen instead of Ubuntu Desktop because the goal is to practice server administration primarily through the command line.

Storage

The Ubuntu installer was configured to use the entire 25 GB virtual disk with LVM.

Disk encryption was not enabled for this initial lab environment.

Networking

The virtual machine received its network configuration through DHCP.

Current interface:

enp0s1

Current IPv4 address:

192.168.64.2/24

The exact IP address may change in the future because it is currently assigned dynamically.

Remote Administration

OpenSSH Server was installed during the Ubuntu installation.

Remote access from the macOS host was successfully tested with:

ssh melina@192.168.64.2

This allows the Ubuntu server to be administered remotely from the macOS Terminal instead of relying exclusively on the UTM console.

Initial System Setup

After installation, the package information and installed packages were updated using:

sudo apt update
sudo apt upgrade

The server was also verified using commands such as:

whoami
hostname
ip addr
uname -a
lsb_release -a
df -h
free -h

Result

The first Linux server of the homelab is now operational and accessible remotely through SSH.

This server will be used to practice:



Linux administration

Users and groups

File permissions

Networking

SSH

Services

Logging

Automation

System hardening

Security monitoring
