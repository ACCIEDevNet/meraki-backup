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

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ACCIEDevNet/meraki-backup.git
   cd meraki-backup
