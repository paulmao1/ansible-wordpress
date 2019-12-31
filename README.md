# WordPress Ansible

This repository contains a playbook for provisioning modern hosting environments geared towards WordPress. 
* User setup
* SSH hardening
* Firewall setup

It will also install the following software:

* Nginx with HTTP/2
* PHP 5
* MariaDB
* Redis
* WP-CLI
* Fail2Ban
* Git

Supported platform:
* Ubuntu16.0.4
* Ubuntu18.0.4


## Usage

1. Configure your [hosts file](https://github.com/paulmao1/ansible-wordpress/blob/master/hosts).

```
[webserver]
10.110.156.15 #www.test.local
```

2. Edit [provision.yml](https://github.com/paulmao1/ansible-wordpress/blob/master/provision.yml) to configure your default user, [hashed](http://docs.ansible.com/ansible/faq.html#how-do-i-generate-crypted-passwords-for-the-user-module) sudo password and local public key path. This will create a new user on the provisioned servers that you can use to gain SSH access.

3. Run playbook:

`ansible-playbook provision.yml`

4. Install wordpress
*  Browser http://www.test.local
*  Create the new file `wp-config-sample.php` in the base directory of your WordPress directory  /var/www/www.test.local
