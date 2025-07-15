# README.md
# AutoTech Philippines - Automotive Shop Management System

A comprehensive web-based management system designed specifically for automotive shops in the Philippines. Built with modern technologies and localized for Philippine business requirements.

## 🚗 Features

### Core Functionality
- **Customer Management (CRM)** - Complete customer profiles with Philippine address structure
- **Vehicle Management** - Track vehicle information, registration, and insurance
- **Appointment Scheduling** - Calendar-based appointment system
- **Work Order Management** - Comprehensive service tracking and documentation
- **Inventory Management** - Parts tracking with automatic reorder alerts
- **Payment Processing** - Support for cash, card, GCash, and bank transfers
- **Digital Service History** - Complete service records accessible via QR code

### Philippines-Specific Features
- **Philippine Address System** - Barangay, City, Province structure
- **Local Phone Number Validation** - +63 format support
- **Philippine Peso (₱) Currency** - All financial calculations in PHP
- **Manila Timezone** - Automatic timezone handling
- **Multi-language Support** - English and Tagalog interfaces
- **Data Privacy Act Compliance** - Philippine privacy law compliance

### Advanced Features
- **Role-based Access Control** - Admin, Manager, Mechanic, Cashier roles
- **Audit Trail** - Complete activity logging for compliance
- **Real-time Notifications** - SMS and email alerts
- **Mobile-responsive Design** - Optimized for tablets and smartphones
- **Customer Portal** - Self-service vehicle history access
- **QR Code Integration** - Quick access to service records

## 🛠 Technology Stack

### Backend
- **Java 17** with **Spring Boot 3.2**
- **PostgreSQL 15** database
- **Redis** for caching and sessions
- **Spring Security** with JWT authentication
- **Docker** containerization

### Frontend
- **React 18** with modern hooks
- **Tailwind CSS** for styling
- **React Query** for data management
- **React Router** for navigation
- **Recharts** for data visualization

### Infrastructure
- **Docker Compose** for orchestration
- **Nginx** reverse proxy with SSL
- **Let's Encrypt** SSL certificates
- **Automated backups** and monitoring

## 🚀 Quick Start

### Prerequisites
- Docker and Docker Compose
- Git
- Domain name (for production SSL)

### Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-repo/autotech-philippines.git
   cd autotech-philippines
   ```

2. **Create environment file**
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

3. **Start development environment**
   ```bash
   docker-compose up -d
   ```

4. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8080/api
   - Health Check: http://localhost:8080/api/actuator/health

### Production Deployment

1. **Prepare server** (Ubuntu 22.04 recommended)
   ```bash
   # Install Docker and Docker Compose
   sudo apt update
   sudo apt install docker.io docker-compose-v2
   sudo usermod -aG docker $USER
   ```

2. **Deploy application**
   ```bash
   # Clone and configure
   git clone https://github.com/your-repo/autotech-philippines.git
   cd autotech-philippines
   cp .env.example .env
   # Configure .env for production
   
   # Run deployment script
   chmod +x scripts/deploy.sh
   ./scripts/deploy.sh
   ```

3. **Setup SSL certificate** (for production domain)
   ```bash
   # SSL is automatically configured in deploy.sh
   # Make sure your domain points to the server
   ```

## 📊 Default Credentials

**System Administrator**
- Username: `admin`
- Password: `admin123`

**Shop Manager**
- Username: `manager`
- Password: `manager123`

**Senior Mechanic**
- Username: `mechanic`
- Password: `mechanic123`

> ⚠️ **Important**: Change all default passwords immediately after deployment!

## 🔧 Configuration

### Environment Variables

Key environment variables to configure:

```env
# Database
DB_PASSWORD=your_secure_password
DB_USERNAME=automotive_user

# Security
JWT_SECRET=your_very_long_jwt_secret_key

# Email (for notifications)
EMAIL_USERNAME=your-email@gmail.com
EMAIL_PASSWORD=your-app-password

# Domain (for production)
DOMAIN=your-domain.com
SSL_EMAIL=admin@your-domain.com
```

### Philippines Localization

The system is pre-configured for Philippine business requirements:
- **Timezone**: Asia/Manila
- **Currency**: Philippine Peso (₱)
- **Phone Format**: +63-9XX-XXX-XXXX
- **Address**: Barangay, City, Province structure
- **Tax Rate**: 12% VAT (configurable)

## 📱 Mobile Access

The system is fully responsive and optimized for:
- **Tablets** - Perfect for shop floor use
- **Smartphones** - Customer portal and basic operations
- **Touch interfaces** - Large buttons for gloved hands
- **High contrast** - Readable in garage lighting

## 🔐 Security Features

- **Multi-factor Authentication** for admin accounts
- **Role-based Access Control** with granular permissions
- **Data Encryption** for sensitive information
- **Audit Logging** for all user activities
- **Session Management** with automatic timeout
- **Input Validation** and SQL injection protection
- **HTTPS Enforcement** with modern SSL/TLS

## 📋 Backup & Recovery

### Automated Backups
```bash
# Daily automated backup (add to crontab)
0 2 * * * /path/to/autotech/scripts/backup.sh

# Manual backup
./scripts/backup.sh
```

### Restore from Backup
```bash
# List available backups
./scripts/restore.sh

# Restore specific backup
./scripts/restore.sh automotive_backup_20241215_140000
```

## 📈 Monitoring

### Health Monitoring
```bash
# Run health check
./scripts/monitor.sh

# Setup automated monitoring (add to crontab)
*/15 * * * * /path/to/autotech/scripts/monitor.sh
```

### System Metrics
- **Application Health**: http://localhost:8080/api/actuator/health
- **Database Status**: Automated PostgreSQL health checks
- **Disk Usage**: Automated monitoring with alerts
- **Service Status**: Docker container health monitoring

## 🆘 Support

### Documentation
- **API Documentation**: http://localhost:8080/swagger-ui.html
- **User Manual**: Available in the application help section
- **Technical Documentation**: See `/docs` directory

### Troubleshooting

**Common Issues:**

1. **Services won't start**
   ```bash
   # Check logs
   docker-compose logs
   
   # Restart services
   docker-compose restart
   ```

2. **Database connection issues**
   ```bash
   # Check database health
   docker exec automotive_postgres pg_isready -U automotive_user
   ```

3. **SSL certificate issues**
   ```bash
   # Renew certificates
   docker exec automotive_nginx certbot renew
   ```

### Contact Information
- **Technical Support**: tech@autotech.ph
- **Business Inquiries**: info@autotech.ph
- **Emergency Contact**: +63-917-123-4567

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

We welcome contributions from the Philippine automotive and tech community!

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 🎯 Roadmap

### Version 2.0 (Q2 2024)
- **Mobile App** - Native iOS and Android apps
- **AI Integration** - Predictive maintenance alerts
- **Advanced Analytics** - Business intelligence dashboard
- **Multi-location Support** - Chain shop management

### Version 2.1 (Q3 2024)
- **Fleet Management** - Corporate customer features
- **Parts Supplier Integration** - Direct ordering system
- **Government Integration** - LTO and DTI reporting
- **Advanced Scheduling** - AI-powered optimization