# Felix Portfolio

A modern, responsive portfolio website built with React, TypeScript, and TailwindCSS, featuring dynamic theme switching, animated particles, and a clean, professional design.

## 🚀 Features

- **Modern Tech Stack**: React 18, TypeScript, TailwindCSS, DaisyUI
- **Theme Switching**: Dark/Light mode with system preference detection
- **Animated Background**: Interactive particle system with mouse interactions
- **Responsive Design**: Mobile-first approach with adaptive layouts
- **Contact Form**: Integrated contact form with email functionality
- **Skill Showcase**: Dynamic progress bars for technical skills
- **Docker Ready**: Containerized deployment with Docker Compose
- **SSL Support**: Let's Encrypt integration for HTTPS

## 🛠️ Tech Stack

### Frontend

- **React 18** - Modern React with hooks
- **TypeScript** - Type-safe JavaScript
- **TailwindCSS** - Utility-first CSS framework
- **DaisyUI** - TailwindCSS components
- **Vite** - Fast build tool
- **tsParticles** - Interactive particle animations

### Backend

- **Docker** - Containerization
- **Nginx** - Web server and reverse proxy
- **Let's Encrypt** - SSL certificate management

### SSL Certificate Setup

### Obtaining certificates

Run Docker Compose to create containers and obtain SSL certificates.

```sh
docker-compose up -d

docker-compose run --rm certbot certonly --webroot --webroot-path=/var/www/certbot -d felix-portfolio.de
```

### Restarting Nginx

After obtaining the certificates, restart the Nginx container to apply the configuration.

```sh
docker-compose restart nginx
```

### Initial setup

```sh
docker build -t certbot-init -f Dockerfile.certbot-init .

docker run --rm -p 80:80 -v "$(pwd)/letsencrypt:/etc/letsencrypt" -v "$(pwd)/certbot:/var/www/certbot" certbot-init
```

This will create folders with certificates, which can then be used in the main docker-compose.

## 📁 Project Structure

```
felix-portfolio/
├── frontend/                 # React application
│   ├── src/
│   │   ├── components/      # Reusable components
│   │   ├── pages/          # Page components
│   │   ├── styles/         # CSS and styling
│   │   └── assets/         # Static assets
│   ├── public/             # Public assets
│   └── package.json
├── backend/                # Python FastAPI backend
│   ├── main.py            # Main application
│   └── requirements.txt
├── docker-compose.yml     # Docker services
├── nginx.conf            # Nginx configuration
└── README.md
```

## 🔗 Links

- **Repository**: [https://github.com/payermann/felix-portfolio](https://github.com/payermann/felix-portfolio)
- **Live Demo**: [https://felix-portfolio.de](https://felix-portfolio.de)

---

### Author

> Felix Fischer

  <a href="#felix-portfolio">
    <img src="https://img.shields.io/badge/Back_to_Top-000000?style=for-the-badge&logo=github&logoColor=white" alt="Back to Top">
  </a>
