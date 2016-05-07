# Tallessa – Effortless Asset Management

## Infrastructure setup via Ansible

## Getting started

## Manual configuration needed

Mostly Scaleway/ARM related.

* Firewall not initially configured due to NBD. See https://community.scaleway.com/t/how-to-configures-iptables-with-input-rules-with-dynamic-nbd/303/22
* Scaleway servers come with IPv6 disabled. Nginx default configuration has IPv6 enabled. Installation of Nginx packages fails due to this. Solution: Remove IPv6 `listen` from `/etc/nginx/sites-available/default`, run `apt-get install nginx` again.
* There is a chicken-egg problem with certificates and virtual hosts. Due to this, create first with `tallessa_frontend_ssl=0 tallessa_site_ssl=0` and after letsencrypt has finished, leave them to defaults.

## License

NOTE: The MIT license only applies to the Ansible scripts. The application itself is GNU AGPLv3 licensed.

    Tallessa – Effortless Asset Management (Infrastructure scripts)
    Copyright © 2016 Santtu Pajukanta

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.

