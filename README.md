# stormshield-commande-utile

## afficher la valeur de débit liée aux interfaces

commande: sfctl -T

![sfctl](https://github.com/DoSec-hash/stormshield-commande-utile/blob/master/gifs/ez.gif)

accéder au menu press "s" puis  "entrer" pour la section souhaité:

![menu](https://github.com/DoSec-hash/stormshield-commande-utile/blob/master/gifs/menu.gif)

##  PING LAN du site A vers le site B (IPSEC)

commande: ping -S ip_source -D ip_destination

![ping](https://github.com/DoSec-hash/stormshield-commande-utile/blob/master/gifs/ping_ipsec.PNG)

##  Lister les ports

commande: portinfo

![portinfo](https://github.com/DoSec-hash/stormshield-commande-utile/blob/master/gifs/portinfo.PNG)

## Lister les connections entrantes pour l'ipsec ( 500 or 4500 ) sur une ip spécifique

commande: tcpdump -tni mvneta0 host 87.158.58.21 and '(port 500 or port 4500)'


## restart service web 

commande: serverd -d

## Vérifier les logs vpn :

commande: tail -f /log/l_vpn

## Récuperer des infos sur les connections d'une ip 

commande: sfctl -s conn -H state=all -H host=93.22.38.149 -v -n -T

## Vérifié la route que prend une ip:

commande:  route get 77.1.23.28

## debug logs ( avancé )

commande: tail -f /log/verbose.sld

## INFO PKI

cat /var/ldap/slapd.conf

## Mettre son ldap en public

 vim ConfigFiles/ldap
 
 modifié le paramétre : Public    1 pour public | 0 pour le local


## Vérifié que la connexion écoute sur n'importe quelle adresse:

FW_BUREAU-SN160A2945895A7>sockstat | grep 636
admin    slapd      1561  6  tcp6   *:636                 *:*
admin    slapd      1561  7  tcp4   *:636                 *:*
FW_BUREAU-SN160A2945895A7>

## activé les logs sld:

Éditer : vim /ConfigFiles/verbose

[sld]
State=0  <----- 1 pour activé
CategoriesDefaultLevel=debug
Categories=SLD_FUNC,SLD_REFRESH,SLD_MODULES,SLD_AUTH_FUNC,SLD_AUTH_PROXYAUTH,SLD_AUTH_HTTP,SLD_AUTH_HTTPS,SLD_AUTH_LOGIN,SLD_AUTH_CONFIG,SLD_AUTH_ERROR,SLD_AUTH_EVENTS,SLD_AUTH_USERS,SLD_AUTH_LDAP,SLD_AUTH_REFRESH,SLD_AUTH_REQ_POST,SLD_AUTH_CERT,SLD_AUTH_XVPN,SLD_AUTH_ENROL,SLD_AUTH_MODULE,SLD_XAUTH_FUNC,SLD_XAUTH_MOD,SLD_WWW_MOD,SLD_WWW_FUNC,SLD_WWW_START,SLD_SERVER_FUNC,SLD_SERVER_MOD,SLD_SERVER_SESSION,SLD_AGENT_COMM,SLD_AGENT_MOD,SLD_SSLRDR_FUNC,SLD_SSLRDR_MOD,SLD_SSLVPN_FUNC,SLD_SSLVPN_MOD,SLD_SSLVPN_REWRITE,SLD_SSLVPN_DHTML,SLD_SSLVPN_ATTR,SLD_SSLVPN_ICA,SLD_SSLVPN_ESC_HTML,SLD_SSLVPN_DUMP,SLD_SSLVPN_TIMING,SLD_SSLVPN_POST,SLD_SSLVPN_COOKIES,SLD_OPENVPN_FUNC,SLD_OPENVPN_SERVER,SLD_OPENVPN_CLIENT,SLD_OPENVPN_VCONN,SLD_OPENVPN_CONFIG,SLD_AUTH_SPONSORING
File=/data/verbose.sld
FileRotate=1
FileMaxSize=5


On relance le service

sld- d

## restart service ldap

enldap


