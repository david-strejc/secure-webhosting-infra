# secure-webhosting-infra


Secure Webhosting Infra serves as repo for gathering tools, techniques and How-Tos to have as secure webhosting for most attacked CMS - WordPress as only can be. One aspect of having fast webhosting is ability to serve more requests and spare more CPU power for defeating potential threats.

## Tols used for securing host

### Virtualmin

### Emails

#### DNSSEC
#### DKIM, SPF
#### Graylisting

#### Fail2Ban

#### Squid 

#### Chroot environment for individual virtual hosts

### PHP configuration hardening

* open_basedir
* memory_limits
* php-fpm
* chroot environment


### Apache2 - mod_security2
### Apache2 - mod_evasive
### Suexec
### Portsentry
### Shorewall
### Postfix - catchall anti user enum


## Attacking tools used for testing host security

### sqlmap
### smtp-user-enum
### nmap

Always scan your hosts with nmap before running Portsentry (Portsentry is not neccessary - but it is fun having fully secured box with assumption everyone who is scanning server using nmap is potential attacker)

### dnsenum

## WordPress plugins
### Sucuri
### Loginizer


## Maintanance

### Backuping
### Alerting

## Speed - why it matters
