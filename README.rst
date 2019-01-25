ansible-role-ara-server
=======================

A work in progress.

Currently supports Ubuntu Bionic and Fedora 29.

This is what the role currently does without changing the defaults:

- Installs pre-requirements
- Creates a user/group for ara
- Creates standard directories (/var/lib/ara, /etc/ara, /var/log/ara)
- Installs ara-server in a virtualenv
- Generates a random secret key if none are provided or already configured
- Configures /etc/ara/settings.yaml
- Installs gunicorn in the same virtualenv
- Sets up a systemd unit file for running ara-server with gunicorn
- Runs SQL migrations (ara-manage migrate)
- Collects static files (ara-manage collectstatic)
- Installs nginx
- Configures nginx to serve static files and reverse proxy gunicorn
