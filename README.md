# forcp
Populate the /etc/netplan/10-ens3.yaml file with the following text.

network:
  version: 2
  renderer: networkd
  ethernets:
    ens3:
      dhcp4: no
      addresses: [149.28.33.44/23,207.148.31.88/32,'2001:19f0:5:2949:5400:01ff:fe7e:196c/64']
      gateway4: 149.28.32.1
      nameservers:
        addresses: [108.61.10.10]
      routes:
      - to: 169.254.0.0/16
        via: 149.28.32.1
        metric: 100

Populate the /etc/netplan/10-ens7.yaml file with the following text.

network:
  version: 2
  renderer: networkd
  ethernets:
    ens7:
      match:
        macaddress: 5a:00:01:7e:19:6c
      mtu: 1450
      dhcp4: no
      addresses: [10.1.96.3/20]

Update networking or reboot.

netplan apply
