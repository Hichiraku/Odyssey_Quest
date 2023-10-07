# 1. Découpage Symétrique

Vue que le pôle informatique est le plus gros pôle, pour un découpage symètrique on va se baser sur son découpage :
2^6 = 64
on retire 2 pour l'adresse réseaux et l'adresse de Broadcast il nous reste donc 
62 adresses

le CIDR sera donc 32-6 = 26

| | Adresse Réseau | Adresse de Broadcast | Adresse de début de plage | Adresse de fin de plage |
| :-------------------: | :-: | :-: | :-: | :-: |
| Pôle Informatique | 172.16.1.0/26 | 172.16.1.63 | 172.16.1.1 | 172.16.1.62|
| Pôle Développement | 172.16.1.64/26 | 172.16.1.127 | 172.16.1.65 | 172.16.1.126|
| Pôle Administratif | 172.16.1.128/26 | 172.16.1.191 | 172.16.1.129 | 172.16.1.190 | 
| Pôle Technicien | 172.16.1.192/26 | 172.16.1.255 | 172.16.1.193 | 172.16.1.254 |

# 2. Découpage Asymétrique

Pour le découpage asymétrique nous allons gerer les pôles en fonction de leur parc matériel. 
Nous commencerons donc par le pôle informatique (50 equipement) puis administratif (20 équipement) puis technicien (15 équipement) et enfin le pôle developpement (12 équipement)

Pôle informatique :
(2^6)-2 = 64-2 = 62
Comme dit dans le découpage symétrique on retire 2 adresses pour l'adresse réseau et l'adresse broadcast
Son CIDR sera 32-6 = 26

Pôle Administratif et Technicien
(2^5)-2 = 32-2 = 30
Son CIDR sera 32-5 = 27

Pôle Développement 
(2^4)-2 = 16-2 = 14
Son CIDR sera 32-4=28

| | Adresse Réseau | Adresse de Broadcast | Adresse de début de plage | Adresse de fin de plage |
| :-: | :-: | :-: | :-: | :-: |
| Pôle Informatique | 172.16.1.0/26 | 172.16.1.63 | 172.16.1.1 | 172.16.1.62 |
| Pôle Administratif | 172.16.1.64/27 | 172.16.1.95 | 172.16.1.65 | 172.16.1.94 |
| Pôle Technicien | 172.16.1.96/27 | 172.16.1.127 | 172.16.1.97 | 172.16.1.126 | 
| Pôle Développement | 172.16.1.128/ | 172.16.1.143 | 172.16.1.129 | 172.16.1.142 |