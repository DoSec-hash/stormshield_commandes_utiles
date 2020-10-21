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
