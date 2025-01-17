
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


**Q.2.3.3**: Pour connaître le type de système de stockage utilisé, utilise la commande suivante : 

**LSBLK**
![Image](https://github.com/user-attachments/assets/0ff46e21-7900-4bda-9e7d-2cccfb3bcf02)







</details>
<HR>
