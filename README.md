# 🚀 Meraki Backup Solution

A Dockerized web application for backing up Cisco Meraki network configurations.

## 📋 Features

- **🔐 Authentication System** - Secure login with customizable credentials
- **🌐 Web Interface** - User-friendly dashboard for managing backups
- **🔍 Network Discovery** - Automatically discovers all networks in your organization
- **📊 Comprehensive Backup** - Backs up:
  - MX, MS, MR device configurations
  - Network settings and routes
  - DHCP server policies
  - Layer 3 interfaces
  - VLAN configurations
  - Firewall rules
- **📁 Organized Storage** - Backups organized by organization/network
- **📥 Downloadable Backups** - ZIP files for easy download
- **📈 Progress Tracking** - Real-time backup progress

## 🐳 Quick Start with Docker

### Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- Meraki API Key (from Meraki Dashboard)
- Meraki Organization ID

## 📦 Docker Image

[![Docker Pulls](https://img.shields.io/docker/pulls/sengar1/meraki-backupv1-meraki-backup)](https://hub.docker.com/r/sengar1/meraki-backupv1-meraki-backup)
[![Docker Image Size](https://img.shields.io/docker/image-size/sengar1/meraki-backupv1-meraki-backup/v1.0)](https://hub.docker.com/r/sengar1/meraki-backupv1-meraki-backup)
[![Docker Version](https://img.shields.io/docker/v/sengar1/meraki-backupv1-meraki-backup/v1.0)](https://hub.docker.com/r/sengar1/meraki-backupv1-meraki-backup)

### Pull Command
```bash
docker pull sengar1/meraki-backupv1-meraki-backup:v1.0
