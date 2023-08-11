# Setup

## Configuration du serveur qui est reveillé

```
sudo apt install ethtool
```

On vérifie que la carte réseau est correctement configurée : 
```
sudo ethtool enp3s0 | egrep "^[[:blank:]]*Wake-on: (g|d)"
```

Pour que ce soit OK : 
```
Wake-on: g
```

Si ce n'est pas le cas : 
```
sudo ethtool -s enp3s0 wol g
```

Pour que la config soit permanente : 
```
post-up /usr/sbin/ethtool -s enp3s0 wol g
post-down /usr/sbin/ethtool -s enp3s0 wol g
```

## Configuration du serveur qui reveil

On install l'outil `wakeonlan`

```
sudo apt install wakeonlan
```

On setup la crontab

```
MAILTO=root                                                                                                                                                                                   
0 12 * * * /usr/bin/wakeonlan -i 192.168.xx.xxx xx:xx:xx:xx:xx:xx
```
