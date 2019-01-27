# Secure Webhosting Infrastructure

![alt text](https://raw.githubusercontent.com/david-strejc/secure-webhosting-infra/master/serure-web-infra.png)

# NEVER LET CONTROL OF YOUR DNS SERVERS UNDER ANYONE ELSE THAN YOU  

I've encountered many "security" companies who have their DNS servers hosted by webhosting companies and calls themselfs security experts. This is madness! DNS controls your company and your life.

Secure Webhosting Infra serves as repo for gathering tools, techniques and How-Tos to have as secure webhosting for most attacked CMS - WordPress as only can be. One aspect of having fast webhosting is ability to serve more requests and spare more CPU power for defeating potential threats.

# Speed as main security feature 

If we think about speed and time when defending webhosting server, we must say time and speed is essential for defending our servers. Typical scenario for attacking website is as follows:

# Attack

* Attacker finds a way to inject a script through SQLi which for now is most used way of attacking website due to: http://www.atomicrbl.com/globe/
* When script is succesfully injected and/or database of users is dumped to attackers machine, attacker wants to crack passwords and proceed with getting full control of server. This kind of action takes time. Cracking passwords and downloading scripts to host is essential for attacker. We are running our PHP sites:
  - in chrooted environment
  - with mountbinds 
  - with Jailkits 
  - php-fpm 
  - WAF 
  - Fail2Ban
  - Portsentry
  - Squid transparent reverse proxy
  - two way firewalls
  - Monitoring, logging, alerting systems in place
* Every action of an attacker requires time. We have not seen a attacker who is able to successfully inject a script into running website and immediatelly take full control of protected system. When chroot env, reverse Squid proxy and other protection mechanisms are in place it takes even longer for skilled attacker to get fammiliar with server environment. And this takes time.
* When we incorporate tools and mechanisms such as Sucuri for protection of WordPress or OSSEC for gethering informations about our server, we got good chance to take action BEFORE attacker gets chance of proceeding further in getting control of our server.
* Making our server as fast as only can be with responding to HTTP requests of regular users, we are saving resources for better security and protection of our box.
* Log monitoring, alerting, file integrity checks, WAF, Squid reverse proxy and other tools gives us more time to take action which will protect us from attacker getting further in compromising our infrastructure.
* Two way firewalls are also good practice for protection of our webservers. 

## Attackers time

* One think you have is attackers time - when someone wants to really attack your servers he needs to make an effort which takes time. If we don't take bots into action, because bot attacks are simplest to defeat, skilled pentester or attacker needs to find as many services and info about your server as he only can. This takes lot of effort and time. 
* Cloacking and masking services is nice way to trick attacker into taking wrong actions and to make a mistake which is than reported through your SIEM system.
* Cloacking and masking services doesn't mean security by obscurity. You need to have services as secure as only can be, have as many protection mechanisms, as only can be and maintain everything up-to-date, working, patched and well organized.
* But when for example you mask all of your services as Micro$oft server, attacker expects to have a MS server to compromise. And he will use tools for exploiting M$ services. Which results into alarms in your protection system.

# Physical servers

We need to find serverhousing company, which can be trusted and this is out of scope of this project. Buying our own hardware is expensive and demands our time and effort for taking care of hardware and not having maximum of "fluid" infrastructure, where we can migrate our services to any kind of provider wordlwide because of IaC (Infrastructure as Code) concept. 

* Most important think when we are selecting hardware and internet infrastructure provider is DDoS protectors. This kind of service is essential for surviving not ethical kind of attack - DDoS.
* Other kind of security threats can "probably" be defeated 

# Tools used for securing host

## Virtualmin

* After 15 yeas spent with U*IX like operating systems I am little bit layzy. And thanks to Webmin I've started my conversion to Unix world. This tool maintains Unix philosophy and is my favorite one. It has nice cli and parses config files like an admin would do. If you are new to Linux world or want to save time - use this tool and learni its way to maintain configs, backups, security and every aspect of well configured Apache or Nignx based web server.

### Emails

* Virtualmin will setup mailservers with unix users and home directories under domains

### DNS

* DNS is the most important thing in any organisation. Person, who controls DNS, controls organisation. Tools like amass and other brute force DNS enumeration tools are hard to defend. Wildcards and views are two techniques I've implemented so far.  


#### DNSSEC

* Enabled DNSSEC by default - only DS records has to be sent to domain registrar

#### DKIM, SPF

* Basic email spam protection in year 2019

#### Graylisting

* Protecting our own mailserver from spammers whith this basic and simple technique

#### SpamAssassin

* Protecting our own mailserver from spammers

### Fail2Ban

IDS/IPS protection system which works in tandem with Shorewall 

* SSH protection agains bruteforce attacks
* Apache DOS protection connected to mod_security2
* Postfix mail protection agains user enumeration
* Dovecot user login protection

### Shorewall

Nice wrapper with easy configuration compared to raw iptables 

* We need small virtual server located fully out of our infrastructure. Google or EC2 are providing small VMs for scanning our infrastructure with nmap. 
* Connected with Fail2Ban
* Logging traffic
* Not mandatory - connect Sorewall and Portsentry

#### Squid 

Squid serves as transparent reverse proxy. Main purpose is to protect attacker from downloading malicious scripts into website. After successfull compromising of a website, attackers want to download scripts and execute them. 

#### Chroot environment for individual virtual hosts

* Jailkit
* Chrooted environment with php-fpm PHP websites 

### PHP configuration hardening

* open_basedir ??? - is this necessary?
* memory_limits
* php-fpm - processes limits
* chroot environment

## Apache2

### mod_security2

* rules OWASP
* updated rules for WordPress functionality

### mod_evasive

* DOS protection

### Shorewall

### Portsentry

* Optional tool for protection agains nmap scans - no regular server needs to make a scan against our publicaly available hosts
* 

### Postfix - catchall anti user enum

* In case of smtp user enum all email addresses are returned to attacker as valid ones. Than attacker is blocked by fail2ban system and responsible people are notified via notification systems about potential sophisticated attack.

#### Defense against smtp-user-enum

* Create catchall user for protected domain so attacker is unable to enum username, because all usernames are valid in this case
* Create limit and rule in fail2ban ips so after too many attemps for user RCPT TO command from one ipaddress in fast rate fail2ban blocks IP from which smtp-user-enum is performed

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

### Monitoring

### Backuping

### Alerting


## Speed - why it matters
