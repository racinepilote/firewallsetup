# firewallsetup
## Fast Firewall Setup

This is a script for setting up a firewall with settings for tarpitting ssh and basic protections that everyone needs.

## Download the rules to /etc/
```
git clone https://github.com/ChrisTitusTech/firewallsetup.git
```

- Checkout branch: like pivpn is different of master
- Copy branch in /etc/firewallsetup
 
## Make the Rules Permenant
### Debian-based Distributions
```
sudo su
apt install iptables-persistent
/etc/init.d/netfilter-persistent save
```
### Arch Linux Distributions
*Use iptable-save which is pre-installed*

## Make the script executable
```
cd /etc/firewallsetup
chmod +x firewall*
```

```
systemctl enable iptables
systemctl enable ip6tables
sudo ./etc/firewallsetup/firewall
```

```
sudo iptables-save > /etc/iptables/rules.v4
sudo iptables-save > /etc/iptables/rules.v6
```


### RHEL / CentOS Distributions
*This is by far the simpliest way to save rules and check them # chkconfig --list | grep iptables*

*Note: chkconfig iptables on only needs to be run once to turn the service on*
```
sudo chkconfig iptables on
sudo service iptables save
```
