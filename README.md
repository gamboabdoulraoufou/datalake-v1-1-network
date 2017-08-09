# datalake-v1-1-network

https://docs.hortonworks.com/HDPDocuments/HDP2/HDP-2.6.1/bk_command-line-installation/content/prepare-environment.html

Use this command to find your active zone(s):

firewall-cmd --get-active-zones
It will say either public, dmz, or something else. You should only apply to the zones required.

In the case of public try:

firewall-cmd --zone=public --add-port=8000/tcp
if you want to make it permanent, try:

firewall-cmd --zone=public --add-port=8000/tcp --permanent
firewall-cmd --zone=public --add-port=8440/tcp --permanent
firewall-cmd --zone=public --add-port=8441/tcp --permanent
Otherwise, substitute dmz for your zone, for example, if your zone is public:

firewall-cmd --zone=public --add-port=2888/tcp --permanent
Then remember to reload the firewall for changes to take effect.

firewall-cmd --reload


hosname -f

# set hostname
vi  /etc/hostname 
hdp-1

/etc/init.d/hostname.sh start


route -n

vi /etc/sysconfig/network 

/etc/sysconfig/network
NETWORKING=yes
HOSTNAME="hdp-1"
GATEWAY="217.182.88.1"
GATEWAYDEV="eth0"
FORWARD_IPV4="yes"

hostnamectl --static set-hostname hdp-1
systemctl restart systemd-hostnamed


vi /etc/hosts
217.182.92.19   hdp-1.exemple.com hdp-1

vi /etc/hostname
hdp-1

hostnamectl --static set-hostname hdp-1

hostname -f

