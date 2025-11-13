# 🦟 Malaria App - Disease Tracking & Prevention System

[![PHP](https://img.shields.io/badge/PHP-8.0+-777BB4?style=flat&logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0+-4479A1?style=flat&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5.2-7952B3?style=flat&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=flat)](LICENSE)

A comprehensive web application designed to track, monitor, and prevent malaria (paludismo) in Costa Rica. This full-stack application provides users with tools for symptom tracking, exposure monitoring, interactive mapping, and educational resources about malaria prevention and treatment.

## ✨ Introduction

Malaria App is a public health initiative developed to mitigate the effects of malaria at the national and global level. The application enables users to:

- **Track Symptoms**: Record and monitor malaria-related symptoms with intensity levels and dates
- **Monitor Exposures**: Log potential disease exposures in specific locations with detailed geographic data
- **Interactive Mapping**: Visualize malaria incidence data across Costa Rica's provinces with historical data
- **AI Chatbot**: Interact with an intelligent chatbot for guidance and symptom assessment
- **Educational Resources**: Access comprehensive information about malaria prevention, symptoms, and treatment

## 🚀 Technologies Used

### Backend
- **PHP 8.0+** - Server-side scripting and application logic
- **MySQL** - Relational database management system
- **PDO** - PHP Data Objects for secure database interactions

### Frontend
- **Bootstrap 5.2** - Responsive CSS framework
- **JavaScript (ES6+)** - Client-side interactivity
- **Leaflet.js** - Interactive mapping library
- **OpenStreetMap** - Map tile provider
- **Font Awesome** - Icon library

### Additional Libraries
- **Google Fonts** - Typography (Montserrat, Roboto Slab)
- **StartBootstrap Forms** - Form validation and styling

## ⚙️ Installation

### Prerequisites

- PHP 8.0 or higher
- MySQL 8.0 or higher
- Apache/Nginx web server
- Composer (optional, for dependency management)

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/malaria-app-prototype.git
cd malaria-app-prototype
```

### Step 2: Database Setup

1. Create a MySQL database:
```sql
CREATE DATABASE db_app_malaria;
```

2. Import the database schema from `dbquery.txt`:
```bash
mysql -u root -p db_app_malaria < dbquery.txt
```

Or manually execute the SQL statements in `dbquery.txt`.

### Step 3: Configure Environment Variables

1. Copy the example environment file:
```bash
cp .env.example .env
```

2. Edit `.env` with your database credentials:
```env
DB_HOST=localhost
DB_NAME=db_app_malaria
DB_USER=root
DB_PASSWORD=your_password
```

3. Update `app/bd.php` to use environment variables (recommended for production):
```php
$servidor = $_ENV['DB_HOST'] ?? 'localhost';
$db = $_ENV['DB_NAME'] ?? 'db_app_malaria';
$usuario = $_ENV['DB_USER'] ?? 'root';
$contrasena = $_ENV['DB_PASSWORD'] ?? '';
```

### Step 4: Configure Web Server

#### Apache
Ensure `mod_rewrite` is enabled and point your document root to the project directory.

#### Nginx
Configure your server block to point to the project directory.

### Step 5: Set Permissions

Ensure the web server has read permissions for all files and write permissions for any directories that need to store uploaded files.

### Step 6: Access the Application

Navigate to your web server URL:
```
http://localhost/malaria-app-prototype
```

## 🧩 Project Structure

```
malaria-app-prototype/
├── app/                      # Application core
│   ├── bd.php               # Database configuration
│   ├── index.php            # Main application dashboard
│   ├── css/                 # Application-specific styles
│   │   └── style.css
│   └── sections/            # Feature modules
│       ├── chatbot/         # Chatbot functionality
│       │   └── newchat.php
│       ├── exposures/       # Exposure tracking
│       │   ├── analisis.php
│       │   ├── crear.php
│       │   └── editar.php
│       ├── symptoms/        # Symptom tracking
│       │   ├── analisis.php
│       │   ├── crear.php
│       │   └── editar.php
│       └── users/           # User management
│           └── crear.php
├── assets/                  # Static assets
│   ├── favicon.ico
│   ├── img/                 # Images
│   │   ├── logos/          # Company logos
│   │   ├── portfolio/      # Portfolio images
│   │   └── team/           # Team member photos
│   └── ...
├── css/                     # Global stylesheets
│   ├── bootstrap.css
│   └── styles.css
├── csv/                     # CSV data files
│   ├── cantones.csv
│   ├── distritos.csv
│   └── provincias.csv
├── js/                      # JavaScript files
│   └── scripts.js
├── templates/               # Reusable templates
│   ├── header.php
│   └── nav.php
├── index.php               # Landing page
├── login.php               # Authentication page
├── logout.php              # Session termination
├── mapa.php                # Map visualization page
├── dbquery.txt             # Database schema
├── .env.example            # Environment variables template
├── .gitignore              # Git ignore rules
├── LICENSE                 # License file
└── README.md               # Project documentation
```

## 🔐 Security Considerations

- **Password Storage**: Currently uses plain text passwords. For production, implement password hashing (e.g., `password_hash()` with `PASSWORD_BCRYPT`)
- **SQL Injection**: Uses PDO with prepared statements to prevent SQL injection
- **Session Security**: Ensure proper session configuration and CSRF protection in production
- **Environment Variables**: Store sensitive credentials in `.env` file (not committed to version control)
- **Input Validation**: Implement server-side validation for all user inputs

## 🚢 Deployment

### Recommended Deployment Platforms

#### Option 1: Traditional Web Hosting
- **cPanel/Shared Hosting**: Upload files via FTP/SFTP
- **VPS**: Deploy on DigitalOcean, Linode, or AWS EC2
- **Dedicated Server**: Full control over server configuration

#### Option 2: Cloud Platforms
- **AWS**: EC2 + RDS (MySQL) + Elastic Beanstalk
- **Google Cloud**: Compute Engine + Cloud SQL
- **Azure**: App Service + Azure Database for MySQL
- **Heroku**: PHP buildpack with ClearDB MySQL addon
- **Render**: PHP web service with MySQL database
- **Railway**: Full-stack deployment platform

#### Option 3: Containerized Deployment
- **Docker**: Containerize the application with PHP-FPM and Nginx
- **Docker Compose**: Orchestrate PHP, MySQL, and Nginx services

### Deployment Checklist

- [ ] Update database credentials in production environment
- [ ] Enable HTTPS/SSL certificate
- [ ] Configure proper error logging (disable error display in production)
- [ ] Set up database backups
- [ ] Implement password hashing
- [ ] Configure CORS headers if needed
- [ ] Set up monitoring and logging
- [ ] Configure firewall rules
- [ ] Enable PHP opcache for performance
- [ ] Set appropriate file permissions

## 🤝 Contributing

This is a proprietary project. For contributions or collaboration inquiries, please contact the Lead Developer.

## 👥 Team

- **Steven Morales Fallas** - Programming & Leadership
- **Camila Montoya** - Design & Organization
- **Fabián Hernández** - Research & Assistance

## 📜 License

This project is proprietary software. All rights reserved.

**Copyright (c) 2023 Steven Morales Fallas**

All rights reserved. Redistribution, modification, reproduction, sublicensing, or any form of transaction (including commercial, educational, or promotional use) involving this repository, its source code, or derived works is strictly prohibited without the explicit and personal written authorization of the Lead Developer, Steven Morales Fallas.

Unauthorized commercial use, resale, or licensing of this repository or its contents is strictly forbidden and will be subject to applicable legal action.

For licensing inquiries, please contact: fallasmoraless@gmail.com

## 📞 Contact

**Steven Morales Fallas**
- Email: fallasmoraless@gmail.com
- Phone: +506 61304830
- Location: Costa Rica

## 🙏 Acknowledgments

- World Health Organization (WHO) for malaria data and information
- OpenStreetMap contributors for map data
- Bootstrap team for the excellent framework
- Leaflet.js developers for the mapping library

---

**Note**: This application is developed for educational and public health purposes. Always consult medical professionals for health-related decisions.

