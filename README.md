# Linux Cloud Security - Group 3

## Publishing and Securing a Simple Web Service on Ubuntu

This repository documents a group project completed as part of the **Linux Cloud Security / Segurança em Infraestruturas Cloud** training module.

The objective of this activity was to prepare a small Linux cloud server, publish a basic web service, validate that it was accessible through the browser and terminal, and document the technical decisions and evidence in GitHub.

## Project Context

The scenario proposed in the activity was a small team needing to publish a web service on a Linux mini-server. The base environment had already been prepared with user organization and permissions, and the group had to choose an appropriate publication route.

The available routes were:

* Nginx
* Apache
* WordPress with Apache
* WordPress with Nginx

The group selected a simple and secure approach: publishing a static HTML page using **Nginx**.

## Selected Solution

* **Service type:** Simple HTML page
* **Publication route:** Nginx
* **Operating system:** Ubuntu Server
* **Environment:** Cloud VPS
* **Protocol:** HTTP
* **Web port:** 80/tcp
* **Remote administration:** SSH
* **SSH port:** 22/tcp
* **Firewall:** UFW
* **Publishing directory:** `/var/www/html`
* **Additional technologies:** None

This option was selected because it is lightweight, easy to validate, and appropriate for an introductory Linux cloud infrastructure scenario. It avoids the additional complexity of PHP, databases, and WordPress while still demonstrating key infrastructure concepts.

## Architecture

The publication flow is:

```text
Client/Browser -> HTTP -> Port 80 -> UFW Firewall -> Nginx -> HTML file
```

The user accesses the server through a browser using HTTP. The request reaches the server on port 80. UFW allows the HTTP traffic, and Nginx responds by serving the HTML file from `/var/www/html`.

SSH access is handled separately:

```text
Administrator -> SSH -> Port 22 -> UFW Firewall -> OpenSSH -> Ubuntu Server
```

SSH was allowed before enabling the firewall to prevent losing remote access to the server.

## Technical Tasks Performed

The group performed the following technical tasks:

* Created a cloud VPS running Ubuntu Server
* Connected to the server using SSH
* Created and used a non-root user with sudo privileges
* Installed and validated Nginx
* Enabled UFW firewall
* Allowed OpenSSH traffic on port 22
* Allowed HTTP traffic on port 80
* Published a simple HTML page in `/var/www/html`
* Validated the service locally with `curl`
* Validated the service through the public IP in a browser
* Collected screenshots as evidence
* Organized the project report, README file, and evidence in GitHub

## Validation

The service was validated using both terminal and browser tests.

Examples of validation steps:

* Check Nginx status:

```bash
systemctl status nginx
```

* Check firewall rules:

```bash
sudo ufw status verbose
```

* Test local HTTP response:

```bash
curl http://localhost
```

* Test public HTTP access:

```bash
curl http://SERVER_PUBLIC_IP
```

* Test browser access:

```text
http://SERVER_PUBLIC_IP
```

The expected result was that the HTML page would be returned by the server and displayed successfully in the browser.

## Security Considerations

The project followed basic security practices:

* SSH access was kept separate from web access.
* UFW was enabled to control incoming traffic.
* OpenSSH was allowed before enabling the firewall to avoid remote lockout.
* Only the required ports were opened:

  * `22/tcp` for SSH
  * `80/tcp` for HTTP
* No private SSH keys, passwords, tokens, payment data, database credentials, or `.env` files were published.
* Screenshots were reviewed before being added to the repository.

## Repository Structure

```text
linux-seguranca-cloud-grupo-3/
└── topico-03/
    └── trabalho-grupo/
        ├── README.md
        ├── grupo-3-publicacao-servico-web-topico-03.pdf
        └── evidencias/
```

## Evidence

The `evidencias/` folder contains screenshots showing:

* Nginx active and running
* UFW firewall rules
* HTML file publication
* Local terminal validation with `curl`
* Public access validation
* Browser access to the published page

## Report

The final report is available at:

```text
topico-03/trabalho-grupo/grupo-3-publicacao-servico-web-topico-03.pdf
```

## Group Members

* Carlina Pinto
* Anne Gomes
* Bruno Veiga

## Conclusion

This project demonstrates the basic workflow for publishing and validating a web service on a Linux cloud server. The group used Ubuntu Server, Nginx, SSH, UFW, HTTP, and GitHub documentation to build a simple but complete infrastructure exercise.

Although the published service was only a static HTML page, the project covered important foundations for Linux system administration, cloud infrastructure, web service deployment, firewall configuration, and technical documentation.
