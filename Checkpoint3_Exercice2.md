
### Exercice 2 : Manipulations pratiques sur VM Linux 

<details>

## Partie 1 : Gestion des utilisateurs
**Q.2.1.1 Sur le serveur, créer un compte pour ton usage personnel**  :

pour la ceation d'un compte personel on utilse la commande 
**usseradd wilder2**
et pour vérifier que le compte est bien été créer on tap

**id wilder2**

![Image](https://github.com/user-attachments/assets/9879f6e5-d1fa-49e2-9b69-2ef6ad4e622a)


**Q.2.1.2 Quelles préconisations proposes-tu concernant ce compte ?**

   * Configurer un mot de passe fort et le  changer régulièrement le mot de passe pour renforcer la sécurité
   * Accorder les privilèges sudo si tu as besoin d'exécuter des commandes
     
## Partie 2 : Configuration de SSH

**Q.2.2.1 :** Pour désactiver l'accès à distance de l'utilisateur root, modifie le fichier de configuration SSH ( nano /etc/ssh/sshd_config) et ajoute ou modifie la ligne suivante **Permit login no**

![Image](https://github.com/user-attachments/assets/1c1365b8-671a-418b-983a-962fcf2aa77a)

**Q.2.2.2 :**
Pour autoriser l'accès à distance uniquement à ton compte personnel, ajoute cette ligne dans le même fichier :

![Image](https://github.com/user-attachments/assets/b37c9798-aedc-460b-8c10-885e12ff9f04)

**Q.2.2.3 Mettre en place une authentification par clé valide et désactiver l'authentification par mot de passe**
on'a juste a **ecrire pubkeyAuthentication yes** 
![Image](https://github.com/user-attachments/assets/808d57cb-05a7-49ed-b72e-71ef5ad694ed)

redémarrer le service SSH après avoir apporté ces modifications avec **sudo systemctl restart sshd**

## Partie 3 : Analyse du stockage



**Q.2.3.1 Pour lister les systèmes de fichiers actuellement montés**
on tap la commande **df -h**
![Image](https://github.com/user-attachments/assets/6bced1b4-21a5-4e03-a388-e99b8732a1fc)

**Q.2.3.2 Quel type de système de stockage ils utilisent ?** 

d'apés la  commande **df -h** le systeme de stockage est LVM 



**Q.2.3.3:  Ajouter un nouveau disque de 8,00 Gio au serveur et réparer le volume RAID**

j'ai utilser les commandes : 

<br>    **fdisk /dev/sdb1**
<br>    **sudo mdadm --manage /dev/md0 --add /dev/sdb1**

**LSBLK**

![Image](https://github.com/user-attachments/assets/9699dec6-5dfd-493f-9be1-79b546440131)

**Q.2.3.4 Ajouter un nouveau volume logique LVM de 2 Gio**

![Image](https://github.com/user-attachments/assets/579415ef-36a9-47d9-ad1d-da01abf4d6ef)

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

![Image](https://github.com/user-attachments/assets/e6001106-bad7-4ec3-a46f-5de72102a0c0)


**Q.2.5.2 Quels types de communications sont autorisées ?**  

* Les connexions établies et connexes.

* Le trafic sur l'interface de bouclage (lo).

* Le trafic SSH (port 22).

* Les paquets ICMP et ICMPv6.

**Q.2.5.3 Quels types sont interdit ?**

* es paquets invalides.

* Tout autre type de trafic qui n'est pas explicitement autorisé par les règles défaut

  **Q.2.5.4**
  ![Image](https://github.com/user-attachments/assets/46b417f6-0f35-4198-bd9e-4e45018db5e2)









</details>
<HR>
