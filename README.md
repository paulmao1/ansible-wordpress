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

2. Edit [environment variable](https://github.com/paulmao1/ansible-wordpress/blob/master/group_vars/all) to configure 
*  your default user, password and local public key path. 
*  DB and wordpress information

3. Run playbook:

`ansible-playbook provision.yml`

4. Install wordpress
*  Browser http://www.test.local
*  Input DB information and generate scripts for wp-config.php, you need to copy it.
*  Touch the new file `wp-config.php` in the base directory of your WordPress directory  /var/www/www.test.local and paste the previous scripts
*  Run Wordpress wizard to finish it
