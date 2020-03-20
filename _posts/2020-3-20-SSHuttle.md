---
layout: post
title: SSHuttle How I set it up to access remote servers...
---
I am splitting the doc into 3 areas,
1. my local machine at home,
2. home router
3. remote server I want to access

## What is SSHuttle? ##
sshuttle is a transparent proxy server that works as a poor man's VPN over ssh. You don't need any admin account on your remote system. It supports DNS tunneling and works with Linux and MacOS platforms. ... But sshuttle is the simplest, but powerful way to setup VPN on any network to which you have SSH access.

### Setup ###
**Local client machine**

```javascript
/* Some pointless Javascript */
var rawr = ["sudo apt install openssh-server"];
```

```javascript
/* Some pointless Javascript */
var rawr = ["systemctl status ssh.service"];
```
![an image alt text]({{ site.baseurl }}/images/sshservice.png "ssh service status")


Next I need to edit the local machine Firewall to allow the new 'reallyhighinboundport/tcp'. To do this I edited the local Firewall via ufw.

What is ufw?  UFW, or uncomplicated firewall, is a frontend for managing firewall rules in Arch Linux, Debian or Ubuntu. UFW is used through the command line (although it has GUIs available), and aims to make firewall configuration easy (or, uncomplicated).

```javascript
/* Some pointless Javascript */
var rawr = ["sudo ufw enable"];
```
Firewall is active and enabled on system startup.  Next add your 'reallyhighinboundport/tcp'

```javascript
/* Some pointless Javascript */
var rawr = ["sudo ufw allow 'reallyhighinboundport/tcp'"];
```
I finally need to edit the open SSH Server port that it needs to listen to, it will not be the ssh port 22, it will need to be the reallyhighinboundport/tcp.

Located in the /etc/ssh/ssh_d_config file you will need to edit the port entry.

**Home Router set up a new inbound port**

made it a really high port number - in this example we will call this 'reallyhighinboundport/tcp'
in addition to this I made the rule that the new 'reallyhighinboundport/tcp' is coming from specific IP or WAN - this would be my remote server public IP address and that route is going to a specific lan IP my local client machine, an example would be:

58582 from WAN a.b.c.d ONLY to LAN a.b.c.d

sudo ufw enable
Firewall is active and enabled on system startup
add 58582
sudo ufw allow 58582/tcp


**Remote Server**
Next we need to create a tunnel from the remote server into your local machine.
The command you need to run the following cmmmand

```javascript
/* Some pointless Javascript */
var rawr = ["ssh -Nv2g -R Some_Other_LargeNumber_PortNotusesd:127.0.0.1:22 username@yourhome_publicIP -p
'reallyhighinboundport/tcp'"];
```
**Local client machine**
back on the local machine back at home I am going to run few tests to see what is going on, am I getting a connection from the remote server.

Test that I can SSH to myself


```javascript
/* Some pointless Javascript */
var rawr = ["ssh-copy-id -p 'reallyhighinboundport/tcp' root@127.0.0.1

ssh -p 'reallyhighinboundport/tcp' root@127.0.0.1"];
```
next enter the password for remote server

Check the incoming connection

```javascript
/* Some pointless Javascript */
var rawr = ["netstat -napt | grep LISTEN"];
```
You should see the inbound port of the Some_Other_LargeNumber_PortNotusesd

Finally SSHuttle

I am going to test with 2 commands

```javascript
/* Some pointless Javascript */
var rawr = ["sshuttle -r root@127.0.0.1:Some_Other_LargeNumber_PortNotusesd 0/0"];
```
that is it you are connect to the remote server and the remote server network.

You could use a more advanced connection command that also uses DNS.

```javascript
/* Some pointless Javascript */
var rawr = ["sshuttle --dns -H -r root@remote_Server_pub_IP:reallyhighinboundport/tcp --syslog --pidfile=/opt/sshuttle/sshuttle.pid 0/0"];
```
Then when prompted - enter the password = remote server
