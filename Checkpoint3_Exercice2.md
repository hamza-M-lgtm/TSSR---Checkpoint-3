
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
![Image](https://github.com/user-attachments/assets/070bf98e-d17c-4100-8965-14cb543795ee)

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

![Image](https://github.com/user-attachments/assets/a34bd9ea-b110-4773-9bbe-e61b1228459c)

**Q.2.3.2 Quel type de système de stockage ils utilisent ?** 

d'apés la  commande **df -h** le systeme de stockage est LVM 



**Q.2.3.3:  Ajouter un nouveau disque de 8,00 Gio au serveur et réparer le volume RAID**

![Image](https://github.com/user-attachments/assets/db2cfdd6-cda2-4ad7-8ab0-136b94fb9805)


pour le raid 
![Image](https://github.com/user-attachments/assets/ba405a0b-683d-4364-8f16-94ae461603ba)


**Q.2.3.4 Ajouter un nouveau volume logique LVM de 2 Gio**

![Image](https://github.com/user-attachments/assets/d59add7f-4f57-4f32-a667-b59692723e9a)

![Image](https://github.com/user-attachments/assets/ecda2319-6d40-4be3-b8b6-ca6cabe64d09)

**Q.2.3.5 Combien d'espace disponible reste-t-il dans le groupe de volume ? :**
il reste 6 Gib 
![Image](https://github.com/user-attachments/assets/21d0a34a-6fa1-467a-8ebc-75aaf01d0227)



## Partie 4 : Sauvegardes

**bareos-dir**  :Son rôle est de gérer le stockage et de planifier les tâches de sauvegarde. Il détermine quoi sauvegarder, comment le faire et à quel moment.

**bareos-sd** : Il reçoit les données de sauvegarde et les écrit sur les périphériques de stockage (disques, bandes, etc.). Il gère également les volumes de stockage et assure la rotation et le recyclage des anciens volumes.

**bareos-fd** : c'est le client et il  est installé sur les machines à sauvegarder et attend les instructions du bareos-dir . Il lit les fichiers et répertoires spécifiés et les envoie au Storage Daemon pour stockage. 


## Partie 5 : Filtrage et analyse réseau

**Q.2.5.1 Quelles sont actuellement les règles appliquées sur Netfilter** 

pour cela il faut vérifier avec la commande **sudo nft list ruleset**

![Image](https://github.com/user-attachments/assets/b6d277dd-200b-422f-95a8-3ad0781ff618)


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

  ![Image](https://github.com/user-attachments/assets/46b417f6-0f35-4198-bd9e-4e45018db5e2)


## Partie 6 : Analyse de logs
**Q.2.6.1 Lister les 10 derniers échecs de connexion ayant eu lieu sur le serveur en indiquant pour chacun**


![Image](https://github.com/user-attachments/assets/0fbd7a9f-4445-40b8-b870-834a3f17f941)









</details>
<HR>
