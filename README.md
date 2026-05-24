# Homelab Linux Server

## Overview

This project documents the setup of a self-hosted Ubuntu Server running on an HP EliteDesk.

The server is configured for headless administration over SSH and will be used as the foundation for future Docker, monitoring, backup, and self-hosted service projects.

## Hardware

- HP EliteDesk
- 16 GB RAM
- Local SSD storage
- Ethernet connection

## Network Setup

- Local IP reserved through router DHCP reservation
- Server IP: `192.168.1.41`
- SSH enabled for remote administration

## Tech Stack

- Ubuntu Server
- OpenSSH
- UFW firewall
- Docker Engine
- Docker Compose
- Linux CLI
- Git

## Setup Process

- Installed Ubuntu Server
- Configured user account and hostname
- Enabled OpenSSH during installation
- Reserved local IP address in router using DHCP reservation
- Verified SSH access from main PC
- Updated system packages
- Installed basic administration tools
- Enabled UFW firewall for SSH access
- Installed Docker Engine using Docker's official apt repository
- Verified Docker installation with `hello-world`
- Verified Docker Compose installation

## Useful Commands

```bash
sudo apt update
sudo apt upgrade -y
sudo apt install -y curl wget git htop unzip net-tools ufw
```

## Firewall

UFW was enabled with OpenSSH allowed to keep remote administration available.

```bash
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status
```

## Docker Installation

Docker Engine was installed using Docker's official apt repository.

Installed components:

- Docker Engine
- Docker CLI
- containerd
- Docker Buildx plugin
- Docker Compose plugin

The installation was verified by running:

```bash
docker run hello-world
docker compose version
```

Docker was configured so the regular user can run Docker commands without using `sudo`.

## Current Status

The server is installed, reachable over SSH, protected with a basic UFW firewall, and has Docker Engine and Docker Compose installed.

It is now ready for future homelab services.

## Future Improvements

- Deploy a Minecraft server using Docker Compose
- Add monitoring with Prometheus and Grafana
- Add automated backups
- Configure Cloudflare DNS for public services
- Add Uptime Kuma for service status monitoring
- Add server hardening and SSH key authentication
