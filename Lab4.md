# Lab 4

## show all connections
```bash
ss -ltpn
```
## display all config setting for the active connection
```bash
nmcli con show Home
```
## show device status
```bash
nmcli device status
```
## display the setting of the enp0s3 interface
```bash
nmcli device show enp0s3
```
## create a static connection with the same IP address, network, prefix and default gateway.
### Name the new connection static-eth0 with ip 172.25.0.11,netmask 255.255.255.0 and gateway 172.25.0.254
```bash
sudo nmcli con add \
  type ethernet                 \
  con-name static-eth0          \
  ifname enp0s3                 \
  ipv4.addresses 172.25.0.11/24 \
  ipv4.gateway 172.25.0.254
```
## modify the new connection to add DNS
```bash
sudo nmcli con modify static-eth0 \
   ipv4.dns "94.140.14.15 94.140.15.16"
```
## activate the new connection
```bash
sudo nmcli con up static-eth0
```
## view the active connection
```bash
nmcli con show static-eth0
```
## verify the ip address using ip command
```bash
ip a s
```
## verify the default gateway
```bash
ip route show
```
## ping the DNS
```bash
ping 94.140.14.15
```
## disable the original connection autostarting at boot
```bash
sudo nmcli con mod static-eth0 connection.autoconnect no
```
## reboot the system
```bash
reboot
```
## view the active connections
```bash
sudo nmcli con show --active
```
## edit the /etc/NetworkManager/system-connections/static-eth0.nmconnection add an additional address of 10.0.0.1/24
```bash
sudo vim /etc/NetworkManager/system-connections/static-eth0.nmconnection
```
## reload the configuration changes
```bash
sudo nmcli con reload
```
## display the current host name
```bash
hostname
```
## display the host name status
```bash
hostnamectl
```
## change the hostname and hostname config file
```bash
sudo hostnamectl set-hostname RHEL9.8
```
## verify the configuration file providing the hostname at network start
```bash
cat /etc/hostname
```