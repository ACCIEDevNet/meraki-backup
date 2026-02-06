🚀 Meraki Backup Solution (No Authentication)
A simple, Dockerized web application to backup your Cisco Meraki network configurations. Just enter your API key and Organization ID to get started!

Docker Pulls Docker Image Size Docker Version

📋 Features
🔐 No Authentication Required - Direct access to backup interface
🌐 Simple Web Interface - Clean, user-friendly dashboard
🔍 Network Discovery - Automatically finds all networks in your organization
📊 Comprehensive Backup - Backs up:
MX, MS, MR device configurations
Network settings and static routes
DHCP server policies
Layer 3 interfaces
📁 Organized Storage - Backups saved by organization/network
📥 Downloadable Backups - ZIP files for easy download
🐳 Quick Start with Docker
Prerequisites
Docker installed
Meraki API Key (from Meraki Dashboard)
Meraki Organization ID
Step 1: Pull the Docker Image
docker pull sengar1/meraki-backup-meraki-backup:v1.0
Step 2: Run the Container
docker run -d \
  --name meraki-backup \
  -p 8080:5000 \
  -v $(pwd)/backups:/app/backups \
  sengar1/meraki-backup-meraki-backup:v1.0
Step 3: Access the Application
Open your browser and go to: http://localhost:8080

No login required! You'll see the backup form immediately.

Step 4: Get Your Meraki Credentials
API Key: Log into Meraki Dashboard

Go to Organization → Settings → API access
Click "Generate API key"
Organization ID: In Meraki Dashboard

Go to Organization → Overview
Organization ID is in the URL or under organization details
🎯 One-Line Installation
docker run -d -p 8080:5000 sengar1/meraki-backup-meraki-backup:v1.0
📸 Interface Preview
┌─────────────────────────────────────────┐
│         MERAKI BACKUP SOLUTION          │
├─────────────────────────────────────────┤
│                                         │
│  Meraki API Key: [___________________]  │
│                                         │
│  Organization ID: [__________________]  │
│                                         │
│          [ Discover Networks ]          │
│                                         │
│  Select Network: [▼ Dropdown List   ]   │
│                                         │
│          [ Start Backup ]               │
│                                         │
└─────────────────────────────────────────┘
⚙️ Configuration Options
Port Configuration
Default port is 8080. To use a different port:

docker run -d -p 3000:5000 sengar1/meraki-backup-meraki-backup:v1.0
Persist Backups
To save backups on your host machine:

docker run -d \
  -p 8080:5000 \
  -v $(pwd)/meraki-backups:/app/backups \
  sengar1/meraki-backup-meraki-backup:v1.0
🚀 Using Docker Compose (Recommended)
# Create docker-compose.yml
cat > docker-compose.yml << 'EOF'
version: '3.8'

services:
  meraki-backup:
    image: sengar1/meraki-backup-meraki-backup:v1.0
    ports:
      - "8080:5000"
    volumes:
      - ./backups:/app/backups
EOF

# Run
docker compose up -d
🔧 How to Use
Step 1: Enter Credentials
Open http://localhost:8080
Enter your Meraki API Key
Enter your Organization ID
Step 2: Discover Networks
Click "Discover Networks"
Wait for the system to fetch all networks from your organization
Step 3: Select Network
Choose a network from the dropdown list
Networks are listed by name with their types (MX, MS, MR)
Step 4: Start Backup
Click "Start Backup"
Watch the progress bar as configurations are backed up
Download the ZIP file when complete
📊 Backup Contents
Each backup includes:

📁 [Network Name]_[Timestamp].zip
├── network_settings.json     # Network configuration
├── devices/                  # Device configurations
│   ├── mx_devices.json      # MX appliances
│   ├── ms_devices.json      # MS switches
│   └── mr_devices.json      # MR access points
├── static_routes.json       # Routing tables
├── dhcp_settings.json       # DHCP configuration
├── l3_interfaces.json       # Layer 3 interfaces
├── vlans.json               # VLAN configurations
├── firewall_rules.json      # Security rules
└── ssids.json               # Wireless SSIDs
🛠️ Management Commands
View Running Container
docker ps
View Logs
docker logs meraki-backup
Stop Container
docker stop meraki-backup
Start Container
docker start meraki-backup
Remove Container
docker rm meraki-backup
Update Image
docker pull sengar1/meraki-backup-meraki-backup:v1.0
🐛 Troubleshooting
Port Already in Use
# Use a different port
docker run -d -p 3000:5000 sengar1/meraki-backup-meraki-backup:v1.0
Can't Access Web Interface
# Check if container is running
docker ps

# Check logs
docker logs meraki-backup
Backup Fails
Verify API key has correct permissions
Check Organization ID is correct
Ensure API key hasn't expired
Check network connectivity
Permission Issues
# Create backups directory
mkdir -p backups
chmod 775 backups
🔒 Security Considerations
⚠️ IMPORTANT: This version has no authentication. Use in secure environments only!

Recommended for:
Local development environments
Secure internal networks
Temporary backup operations
Not recommended for:
Public internet exposure
Production environments without additional security
Multi-user environments
📄 API Requirements
Meraki API Key
Generate from Meraki Dashboard → Organization → Settings → API access
Ensure it has read-only or read-write permissions
API key must have access to the target organization
Organization ID
Found in Meraki Dashboard → Organization → Overview
Can also be found in the URL: https://dashboard.meraki.com/o/{orgId}/...
🚀 Quick Deployment Script
#!/bin/bash
echo "🚀 Deploying Meraki Backup..."
echo "=============================="

# Pull image
docker pull sengar1/meraki-backup-meraki-backup:v1.0

# Create backups directory
mkdir -p meraki-backups

# Run container
docker run -d \
  --name meraki-backup \
  -p 8080:5000 \
  -v $(pwd)/meraki-backups:/app/backups \
  sengar1/meraki-backup-meraki-backup:v1.0

echo "✅ Deployment complete!"
echo "🌐 Access at: http://localhost:8080"
echo "📁 Backups stored in: ./meraki-backups/"
Save as deploy.sh, make executable: chmod +x deploy.sh, then run: ./deploy.sh

📱 Browser Compatibility
✅ Chrome (latest)
✅ Firefox (latest)
✅ Safari (latest)
✅ Edge (latest)
✅ Mobile browsers
🔄 Update Instructions
# Pull latest version
docker pull sengar1/meraki-backup-meraki-backup:v1.0

# Stop and remove old container
docker stop meraki-backup
docker rm meraki-backup

# Start new container
docker run -d --name meraki-backup -p 8080:5000 sengar1/meraki-backup-meraki-backup:v1.0
📚 Resources
Meraki API Documentation
Docker Documentation
Flask Documentation
📄 License
MIT License - See LICENSE file for details

🤝 Contributing
Fork the repository
Create a feature branch
Commit your changes
Push to the branch
Open a Pull Request
📧 Support
For issues and questions:

Check the troubleshooting section above
Ensure Docker is running properly
Verify Meraki API credentials
Docker Hub: https://hub.docker.com/r/sengar1/meraki-backup-meraki-backup
Image: sengar1/meraki-backup-meraki-backup:v1.0

Quick Command: docker run -p 8080:5000 sengar1/meraki-backup-meraki-backup:v1.0

Built with ❤️ using Flask, Docker, and Meraki API
