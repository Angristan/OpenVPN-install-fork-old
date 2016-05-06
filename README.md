##openvpn-install
OpenVPN [road warrior](http://en.wikipedia.org/wiki/Road_warrior_%28computing%29) installer for Debian, Ubuntu and CentOS.

Ce script vous permet d'installer un serveur OpenVPN (Virtual Private Network) rapidement sans que vous n'ayez besoin de vous compliquer la tâche.

##Fork
Cette copie inclue :
- Aucune log (pas de trace)
- Pas de compression [compression is a vector for oracle attacks, e.g. CRIME or BREACH](https://github.com/BetterCrypto/Applied-Crypto-Hardening/pull/91#issuecomment-75388575)
- Une meilleure protection (au niveau du chiffrement des flux)
- TLS 1.2 seulement (meilleure technique actuelle)
- AES-256-CBC et SHA-512 pour HMAC (au lieu de BF-128-CBC and SHA1)
- [FDN's DNS Servers](http://www.fdn.fr/actions/dns/)
- Nearest [OpenNIC DNS Servers](https://www.opennicproject.org/)
- OpenVPN à jour, merci à  [EPEL](http://fedoraproject.org/wiki/EPEL) et [swupdate.openvpn.net](https://community.openvpn.net/openvpn/wiki/OpenvpnSoftwareRepos)
- Toutes les fonctionnalités du [script original](https://github.com/Nyr/openvpn-install) (les contributeurs regardent régulièrement pour mettre à jour le script.)

## Variants

Quand vous lancez le script, deux modes vous sont proposés. Les deux modes fonctionnent aussi bien l'un que l'autre, mais *slow* a la plus haute sécurité, donc cela risque de prendre plus de temps.

Si vous utilisez juste votre serveur VPN à la maison, vous devriez peut-être utiliser *Fast*. Mais si vous utilisez un réseau public (fast food par exemple), vous devriez impérativement choisir *Slow*.

Notez que *Fast* est très sécurisé, bien qu'il le soit moins que *Slow*.

### Slow (chiffrement fort)
Fonctionnalités :
- 4096 bits RSA private key
- 4096 bits Diffie-Hellman key
- 256 bits AES-GCM
- SHA-384 RSA certificate

### Fast (chiffrement moyen)
Features :
- 2048 bits RSA private key
- 2048 bits Diffie-Hellman key
- 128 bits AES-GCM
- SHA-256 RSA certificate

## Compatibilités

Le script est écrit pour fonctionner sous :
- Debian 7
- Debian 8
- Ubuntu 12.04 LTS
- Ubuntu 14.04 LTS
- Ubuntu 15.10
- CentOS 6
- CentOS 7

Chacun de ces OS est copatible, des tests ont été effectués.

##Installation

Lancez le script par ces lignes de commandes :

```
wget --no-check-certificate https://bit.ly/ovpn-install -O openvpn-install.sh
chmod +x openvpn-install.sh
./openvpn-install.sh
```

Une fois terminé, vous pouvez ajouter un utilisateur, en supprimer, désintaller OpenVPN.



## Licence

Basé sur le travail de [Nyr](https://github.com/Nyr/openvpn-install)

[MIT Licence](https://raw.githubusercontent.com/Angristan/openvpn-install-nyr/master/LICENSE)
