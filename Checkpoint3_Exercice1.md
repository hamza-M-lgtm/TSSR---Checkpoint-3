### Partie 1 : Gestion des utilisateurs
<details>
##Partie 1 : Gestion des utilisateurs:

**Q.1.1.1 Créer l'utilisateur Lionel Lemarchand avec les même attribut de société que **Kelly Rhameur** :**
on cemence par trouver le compte de Kelly Rhameur on ouvre notre active derectory > tools > active directory Users and Computer > TTSR.lan >LabUsers > direction RH  ![Image](https://github.com/user-attachments/assets/26a98fff-901b-46d1-8a4f-125f0f1a552f)

pour la creation du compte **Lionel Lemarchand** 
Clique droit sur DirectionDesRessourcesHumaine > New> User> en rentre les information puis on valide a la fin et en clique sur terminer  bien sur on copier les attribue du compte **Kelly Rhameur** et on les colle dans le compte de **Lionel Lemarchand**
![Image](https://github.com/user-attachments/assets/49ede6d2-5b81-477f-b53b-6cb83a76fc1f)

**Q.1.1.2 Créer une OU DeactivatedUsers et déplace le compte désactivé de Kelly Rhameur dedans**

clique droit sur notre domaine TSSR.lan  > NEW > Organizational Unit et en rentre le nom de  **DeactivatedUsers**

![Image](https://github.com/user-attachments/assets/74d241e5-e181-42ab-9d78-39407473003b)

![Image](https://github.com/user-attachments/assets/175df7b0-50d5-467e-9b0f-f5102250caef)

**Q.1.1.3 Modifier le groupe de l'OU dans laquelle était Kelly Rhameur en conséquence.**

pour modifier le groupe de Kelly Rhameur on deplace sont compte dans **DeactivatedUsers** on fait clique droit sur le compte de **Kelly Rhameur** > move > Et on sélectionne **DeactivatedUsers** dans la fenêtre qui va s'ouvrir.et on clique ok 
![Image](https://github.com/user-attachments/assets/fca12de5-c9fa-4725-8b86-0679e4ef697c)

### Partie 2 : Restriction utilisateurs
Q.1.2.1 Faire en sorte que l'utilisateur Gabriel Ghul ne puisse se connecter que du lundi au vendredi, de 7h à 17h.

Tout d'abord, nous allons créer un OU afin de déplacer **l'utilisateur Gabriel Ghul** pour mettre en œuvre la restriction.
![Image](https://github.com/user-attachments/assets/885a0e75-507e-477d-8d29-5114cd89888e)

* puis on vas créer une gpo pour Gabriel Ghul ne puisse se connecter que du lundi au vendredi, de 7h à 17h 

* Créer une nouvelle stratégie de groupe  Dans le Gestionnaire de stratégies de groupe, clique avec le bouton droit sur "Configuration de l'ordinateur", 
 sélectionne "Nouvelle stratégie de groupe"
* Configurer la stratégie de connexion : Dans la fenêtre qui s'ouvre, donne un nom à ta stratégie (par exemple, "Restriction Connexion Gabriel Ghul") et clique sur 
 "Suivant"
![Image](https://github.com/user-attachments/assets/85be2bea-7d7c-4375-b694-829fc7db1bec)

* Sélectionner l'unité organisationnelle (OU) : Choisis l'OU où se trouve le compte de Gabriel Ghul et clique sur "Suivant".

* Configurer les paramètres de connexion : Dans la fenêtre des paramètres de stratégie, coche la case "Configurer les heures de connexion" et clique sur "Modifier".

* Définir les heures de connexion : Dans la fenêtre qui s'ouvre, définis les heures de connexion autorisées du lundi au vendredi, de 7h à 17h. Clique sur "OK" pour 
  enregistrer les modifications.

* Appliquer la stratégie : Clique sur "Suivant" puis sur "Terminer" pour appliquer la stratégie de groupe.












</details>
<HR>
