# Tallessa – Effortless Asset Management

## Infrastructure setup via Ansible

## Getting started

## Manual configuration needed

Mostly Scaleway/ARM related.

* Firewall not initially configured due to NBD. See https://community.scaleway.com/t/how-to-configures-iptables-with-input-rules-with-dynamic-nbd/303/22
* Scaleway servers come with IPv6 disabled. Nginx default configuration has IPv6 enabled. Installation of Nginx packages fails due to this. Solution: Remove IPv6 `listen` from `/etc/nginx/sites-available/default`, run `apt-get install nginx` again.
* There is a chicken-egg problem with certificates and virtual hosts. Due to this, create first with `tallessa_frontend_ssl=0 tallessa_site_ssl=0` and after letsencrypt has finished, leave them to defaults.
