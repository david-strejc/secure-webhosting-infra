# secure-webhosting-infra


Secure Webhosting Infra serves as repo for gathering tools, techniques and How-Tos to have as secure webhosting for most attacked CMS - WordPress as only can be. One aspect of having fast webhosting is ability to serve more requests and spare more CPU power for defeating potential threats.

# Speed as main security feature 

If we think about speed and time when defending webhosting server, we must say time and speed is essential for defending our servers. Typical scenario for attacking website is as follows:

* Attacker finds a way to inject a script through SQLi which for now is most used way of attacking website due to: http://www.atomicrbl.com/globe/
* When script is succesfully injected and/or database of users is dumped to attackers machine, attacker wants to crack passwords and proceed with getting full control of server. This kind of action takes time. Cracking passwords and downloading scripts to host is essential for attacker. We are running our PHP sites in chrooted environment with mountbinds and Jailkits


## Tols used for securing host

### Virtualmin

### Emails

#### DNSSEC
#### DKIM, SPF
#### Graylisting

#### Fail2Ban

#### Squid 

Squid serves as transparent reverse proxy. Main purpose is to protect attacker from downloading malicious scripts into website. After successfull compromising of a website, attackers want to download scripts and execute them. 

#### Chroot environment for individual virtual hosts

### PHP configuration hardening

* open_basedir
* memory_limits
* php-fpm
* chroot environment

## Apache2 - 

### mod_security2

* rules OWASP
* updated rules for WordPress

### mod_evasive

### Shorewall
### Portsentry

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
