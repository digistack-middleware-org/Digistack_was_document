# Change IP in Vmware NAT 

```
nmcli connection show
ip addr
```
```
sudo nmcli con mod ens160 \
ipv4.addresses <New_IP_Address>/24 \
ipv4.gateway 192.168.10.2 \
ipv4.dns "8.8.8.8 1.1.1.1" \
ipv4.method manual
```

```
sudo nmcli con down ens160
sudo nmcli con up ens160
```

```
sudo systemctl restart NetworkManager
```

#### Verify

```
ip addr show ens160
ip route 
```
