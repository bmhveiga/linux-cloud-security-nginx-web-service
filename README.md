# Linux Cloud Security - Group 3

## Publishing and Securing a WordPress Web Service on Ubuntu

This repository documents a group project completed as part of the **Linux Cloud Security / Segurança em Infraestruturas Cloud** training module, together with the practical continuation of that work into a live WordPress deployment.

The objective was to prepare a Linux cloud server, securely expose a web service, validate connectivity and service availability, and document the infrastructure and security decisions involved.

The environment was later extended into the WordPress deployment currently used to host my personal IT portfolio.

---

## Project Context

The original activity involved publishing a web service on a Linux cloud VPS.

The available implementation routes included:

- Nginx
- Apache
- WordPress with Apache
- WordPress with Nginx

The project evolved into a **WordPress deployment using Nginx**, adding PHP and MariaDB to the original Linux server and web-service configuration.

This provided practical experience not only with publishing a web page, but with configuring and maintaining the infrastructure required by a real content-management system.

---

## Final Solution

- **Application:** WordPress
- **Web server:** Nginx
- **Operating system:** Ubuntu Server
- **Environment:** Cloud VPS
- **Database:** MariaDB
- **Server-side runtime:** PHP
- **Remote administration:** SSH
- **Firewall:** UFW
- **Web protocols:** HTTP / HTTPS
- **Web root:** `/var/www/html`
- **Version control / documentation:** GitHub

The resulting server is used to host my personal IT portfolio.

---

## Architecture

The application follows a standard Linux web-stack architecture:

```text
User / Browser
      |
      v
   HTTP/HTTPS
      |
      v
  UFW Firewall
      |
      v
     Nginx
      |
      v
     PHP
      |
      v
   WordPress
      |
      v
   MariaDB
