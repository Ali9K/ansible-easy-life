Ansible Role: NGINX (LEMP Stack - NGINX Container Setup)
This Ansible role sets up an NGINX Docker container as part of a LEMP(Linux,Nginx,Mysql, and python) stack. It creates a configuration directory, copies an NGINX config template, and launches the container with specific settings.

What This Role Does
Creates a directory for NGINX configuration files.

Copies an NGINX configuration file from a Jinja2 template.

Starts an NGINX container using the official Docker image.

Default Variables
The following default variables are expected and can be overridden as needed:

yaml
Copy
Edit
PATH: /etc/nginx/sites-available/lemp
NGINX_VERSION: latest
NGINX_PORT: 2380
NETWORK: lempnet
Description of Variables
Variable	Description
PATH	Filesystem path to store the NGINX config
NGINX_VERSION	Version of the NGINX image (e.g., latest, 1.25)
NGINX_PORT	Host port mapped to container port 80
NETWORK	Docker network the container should join

Tags
You can use tags to execute specific parts of the role:

nginx-dir: Only create the configuration directory

nginx-templates: Only copy the NGINX config file

nginx-run: Only start the Docker container

Example Playbook
yaml
Copy
Edit
- hosts: localhost
  become: yes
  roles:
    - role: your_role_name
      vars:
        PATH: /etc/nginx/sites-available/lemp
        NGINX_VERSION: latest
        NGINX_PORT: 2380
        NETWORK: lempnet
Requirements
Docker installed on the host

Docker SDK for Python (pip install docker)

The Docker network lempnet must exist before running the role. You can create it with:

bash
Copy
Edit
docker network create lempnet
Template File
Ensure you have a Jinja2 template named nginx.conf.j2 in your templates/ directory.

License
MIT

Author
Ali9K
