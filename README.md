# secure-webhosting-infra


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
* Cloacking and masking services doesn't mean security by obscurity. You need to have services as secure as only can be, have as many protection mechanisms, as only can be and maintain everything up-to-date, working, patched and well maintained.
* But when for example you mask all of your services as Micro$oft server, attacker expects to have a MS server to compromise. And he will use tools for exploiting M$ services. Which results into alarms in your protection system.

# Physical servers

We need to find serverhousing company, which can be trusted and this is out of scope of this project. Buying our own hardware is expensive and demands our time and effort for taking care of hardware and not having maximum of "fluid" infrastructure, where we can migrate our services to any kind of provider wordlwide because of IaC (Infrastructure as Code) concept. 

* Most important think when we are selecting hardware and internet infrastructure provider is DDoS protectors. This kind of service is essential for surviving not ethical kind of attack - DDoS.
* Other kind of security threats can "probably" be defeated 

## Tools used for securing host

### Virtualmin

### Emails

#### DNSSEC

#### DKIM, SPF

* Basic email spam protection in year 2019

#### Graylisting

* Protecting our own mailser

#### SpamAssassin

### Fail2Ban

#### Squid 

Squid serves as transparent reverse proxy. Main purpose is to protect attacker from downloading malicious scripts into website. After successfull compromising of a website, attackers want to download scripts and execute them. 

#### Chroot environment for individual virtual hosts

### PHP configuration hardening

* open_basedir
* memory_limits
* php-fpm
* chroot environment

## Apache2

### mod_security2

* rules OWASP
* updated rules for WordPress functionality

### mod_evasive

* DOS protection

### Shorewall

* We need small virtual server located fully out of our infrastructure. Google or EC2 are providing small VMs for scanning our infrastructure with nmap. 


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

### Monitoring

### Backuping

### Alerting


## Speed - why it matters
