### Partie 1 : Gestion des utilisateurs
<details>
##Partie 1 : Gestion des utilisateurs:

**Q.1.1.1 Créer l'utilisateur Lionel Lemarchand avec les même attribut de société que **Kelly Rhameur** :**

pour la creation du compte **Lionel Lemarchand** 
Clique droit sur DirectionDesRessourcesHumaine > New> User> en rentre les information puis on valide a la fin et en clique sur terminer . voir l'image pour les attributs 
![Image](https://github.com/user-attachments/assets/0dfb4e5d-a963-46d6-8342-b130d8c75d57)


**Q.1.1.2 Créer une OU DeactivatedUsers et déplace le compte désactivé de Kelly Rhameur dedans**

clique droit sur notre domaine TSSR.lan  > NEW > Organizational Unit et en rentre le nom de  **DeactivatedUsers**

![Image](https://github.com/user-attachments/assets/74d241e5-e181-42ab-9d78-39407473003b)

![Image](https://github.com/user-attachments/assets/175df7b0-50d5-467e-9b0f-f5102250caef)

**Q.1.1.3 Modifier le groupe de l'OU dans laquelle était Kelly Rhameur en conséquence.**

![Image](https://github.com/user-attachments/assets/da13e6ca-7748-4eed-8027-7353caf1c630)

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

**Q.1.2.2 De même, bloquer sa connexion au seul ordinateur CLIENT01**
![Image](https://github.com/user-attachments/assets/2a4fa3ce-dab3-4996-8a2a-224af821890e)

**Q.1.2.3 Mettre en place une stratégie de mot de passe pour durcir les comptes des utilisateurs de l'OU LabUsers** 
* Ouvrez la console Group Policy Management (GPMC).

* Clic droit sur l'OU LabUsers et sélectionnez "Create a GPO in this domain, and Link it here...".

*  Nommez la nouvelle GPO (par exemple, "LabUsers Password Policy") et cliquez sur "OK".
![Image](https://github.com/user-attachments/assets/76f487d6-32a6-48d6-bf5b-95b3365a31aa)


* Clic droit sur la nouvelle GPO créée et sélectionnez "Edit".

* Dans l'éditeur de Group Policy Management, naviguez jusqu'à Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > 
* Password Policy.

* Configurez les paramètres de politique de mot de passe selon les besoins, par exemple :

* Enforce password history : 24 mots de passe mémorisés.

* Maximum password age : 30 jours.

* Minimum password age : 1 jour.

* Minimum password length : 12 caractères.

* Password must meet complexity requirements : Activé.

* Store passwords using reversible encryption : Désactivé.

* Fermez l'éditeur de Group Policy Management une fois les paramètres configurés

![Image](https://github.com/user-attachments/assets/3afee39a-3be1-4289-b980-6899a0789d31)









</details>
<HR>
