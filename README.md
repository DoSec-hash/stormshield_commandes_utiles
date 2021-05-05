# stormshield_commande_utiles

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

## Vérifié la route par defaut:

commande:  route get 77.1.23.28

## Mettre son ldap en public

 vim ConfigFiles/ldap
 
 modifié le paramétre : Public    1 pour public | 0 pour le local


## Vérifié que la connexion écoute sur n'importe quelle adresse:

FW_BUREAU-SN160A2945895A7> sockstat | grep 636

admin    slapd      1561  6  tcp6   *:636                 *:*
admin    slapd      1561  7  tcp4   *:636                 *:*

FW_BUREAU-SN160A2945895A7>

## redémarrer le service ldap

enldap

## afficher les routes connues et appliquées par l'ASQ

sfctl -s route

##  afficher la table ARP

arp -an

## suprimmer le cache arp

arp -a -d




