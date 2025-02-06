
### Exercice 2 : Manipulations pratiques sur VM Linux 

<details>

## Partie 1 : Gestion des utilisateurs
**Q.2.1.1 Sur le serveur, créer un compte pour ton usage personnel**  :

pour la ceation d'un compte personel on utilse la commande 
**useradd wilder2**
et pour vérifier que le compte est bien été créer on tap

**id wilder2**

![Image](https://github.com/user-attachments/assets/9879f6e5-d1fa-49e2-9b69-2ef6ad4e622a)


**Q.2.1.2 Quelles préconisations proposes-tu concernant ce compte ?**

   * Configurer un mot de passe fort et le  changer régulièrement le mot de passe pour renforcer la sécurité
   * Accorder les privilèges sudo si tu as besoin d'exécuter des commandes
     
## Partie 2 : Configuration de SSH

**Q.2.2.1 :** Pour désactiver l'accès à distance de l'utilisateur root, modifie le fichier de configuration SSH ( nano /etc/ssh/sshd_config) et ajoute ou modifie

**permitRootLoging**
<P ALIGN="center"><IMG src="ressources/Exercice 2 - Manipulations pratiques sur VM Linux/Capture d'écran_Q.2.2.1 Désactiver l'accès root à distance.png" width=500></P>

**Q.2.2.2 :**
Pour autoriser l'accès à distance uniquement à ton compte personnel, ajoute cette ligne dans le même fichier :

![Image](https://github.com/user-attachments/assets/b37c9798-aedc-460b-8c10-885e12ff9f04)

**Q.2.2.3 Mettre en place une authentification par clé valide et désactiver l'authentification par mot de passe**
on'a juste a **ecrire pubkeyAuthentication yes** 
![Image](https://github.com/user-attachments/assets/808d57cb-05a7-49ed-b72e-71ef5ad694ed)

redémarrer le service SSH après avoir apporté ces modifications avec **sudo systemctl restart sshd**

## Partie 3 : Analyse du stockage



**Q.2.3.1 Pour lister les systèmes de fichiers actuellement montés**
on tap la commande **findmnt**

<P ALIGN="center"><IMG src="ressources/Exercice 2 - Manipulations pratiques sur VM Linux/Q.2.3.1 Systèmes de fichiers montés.png" width=500></P>

**Q.2.3.2 Quel type de système de stockage ils utilisent ?** 

d'apés la  commande **df -h** le systeme de stockage est LVM 



**Q.2.3.3:  Ajouter un nouveau disque de 8,00 Gio au serveur et réparer le volume RAID**

<P ALIGN="center"><IMG src="ressources/Capture d'écran.Q.2.3.3 .png" width=500></P>



pour le raid 
<P ALIGN="center"><IMG src="ressources/Nouveau dossier/Capture d'écran Raid 8G.png" width=500></P>


**Q.2.3.4 Ajouter un nouveau volume logique LVM de 2 Gio**

<P ALIGN="center"><IMG src="ressources/Exercice 2 - Manipulations pratiques sur VM Linux/Q.2.3.4 Ajouter un volume LVM pour les sauvegardes_A.png" width=500></P>

![Image](https://github.com/user-attachments/assets/ecda2319-6d40-4be3-b8b6-ca6cabe64d09)

**Q.2.3.5 Combien d'espace disponible reste-t-il dans le groupe de volume ? :**
il reste 6 Gib 

<P ALIGN="center"><IMG src="ressources/Exercice 2 - Manipulations pratiques sur VM Linux/Q.2.3.5 Espace disponible dans le groupe de volume.png" width=500></P>


## Partie 4 : Sauvegardes

**bareos-dir**  :Son rôle est de gérer le stockage et de planifier les tâches de sauvegarde. Il détermine quoi sauvegarder, comment le faire et à quel moment.

**bareos-sd** : Il reçoit les données de sauvegarde et les écrit sur les périphériques de stockage (disques, bandes, etc.). Il gère également les volumes de stockage et assure la rotation et le recyclage des anciens volumes.

**bareos-fd** : c'est le client et il  est installé sur les machines à sauvegarder et attend les instructions du bareos-dir . Il lit les fichiers et répertoires spécifiés et les envoie au Storage Daemon pour stockage. 


## Partie 5 : Filtrage et analyse réseau

**Q.2.5.1 Quelles sont actuellement les règles appliquées sur Netfilter** 

pour cela il faut vérifier avec la commande **sudo nft list ruleset**

<P ALIGN="center"><IMG src="ressources/Exercice 2 - Manipulations pratiques sur VM Linux/Q.2.5.1 Règles appliquées sur Netfilter.png" width=500></P>


**Q.2.5.2 Quels types de communications sont autorisées ?**  

* Les connexions établies et connexes.

* Le trafic sur l'interface de bouclage (lo).

* Le trafic SSH (port 22).

* Les paquets ICMP et ICMPv6.

**Q.2.5.3 Quels types sont interdit ?**

* es paquets invalides.

* Tout autre type de trafic qui n'est pas explicitement autorisé par les règles défaut

  **Q.2.5.4**

<br>
<P ALIGN="center"><IMG src="ressources/Exercice 2 - Manipulations pratiques sur VM Linux/Q.2.5.4 Ajouter des règles pour Bareos.png" width=500></P>
  

## Partie 6 : Analyse de logs
**Q.2.6.1 Lister les 10 derniers échecs de connexion ayant eu lieu sur le serveur en indiquant pour chacun**


<P ALIGN="center"><IMG src="ressources/Exercice 2 - Manipulations pratiques sur VM Linux/Q.2.6.1 Lister les 10 derniers échecs de connexion.png" width=500></P>









</details>
<HR>
