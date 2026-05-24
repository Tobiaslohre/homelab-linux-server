# Homelab Linux Server

## Overview

This project documents the setup of a self-hosted Ubuntu Server running on an HP EliteDesk. The server is configured for headless administration over SSH and will be used as the foundation for future Docker, monitoring, backup, and self-hosted service projects.

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

## Current Status

The server is installed, reachable over SSH, and ready for future homelab services.

Future Improvements
Install Docker and Docker Compose
Deploy a Minecraft server using containers
Add monitoring with Prometheus and Grafana
Add automated backups
Configure Cloudflare DNS for public services

## Useful Commands

```bash
sudo apt update
sudo apt upgrade -y
sudo apt install -y curl wget git htop unzip net-tools ufw
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status```

## Firewall

UFW was enabled with OpenSSH allowed to keep remote administration available.

```bash
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status

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

Docker was configured so the regular user can run Docker commands without using sudo.


Commit dette:

```bash
git add README.md
git commit -m "document docker installation"
git push

