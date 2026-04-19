# Projet Active Directory – keran.local

## Présentation

Ce projet consiste à déployer une **infrastructure Active Directory complète** dans un environnement virtuel afin de simuler le fonctionnement d’une entreprise.

L’objectif était de mettre en place un **contrôleur de domaine**, d’organiser les utilisateurs et les ordinateurs dans l’annuaire, de sécuriser des **partages réseau**, puis d’automatiser certaines règles via des **GPO**.

---

## Objectifs du projet

- Installer et configurer **Windows Server**
- Déployer le rôle **Active Directory Domain Services (AD DS)**
- Créer le domaine **`keran.local`**
- Structurer l’annuaire avec des **OU** métiers
- Créer des **utilisateurs**, **groupes** et **ordinateurs**
- Mettre en place des **partages réseau** avec permissions de partage et NTFS
- Joindre des postes **Windows 11** au domaine
- Déployer des **GPO** de sécurité et de personnalisation
- Vérifier le bon fonctionnement de l’environnement par des tests concrets

---

## Environnement technique

- **Hyperviseur :** Oracle VirtualBox
- **Serveur :** Windows Server 2025
- **Postes clients :** Windows 11
- **Domaine :** `keran.local`
- **Services :** AD DS, DNS, GPO, SMB / NTFS
- **Réseau :** communication interne validée entre machines virtuelles

---

## Architecture logique

### Domaine
- `keran.local`

### OU créées
- Comptabilité
- IT
- Direction
- Marketing
- Ressources humaines
- Ordinateurs

### Exemples d’objets créés
- Utilisateurs : Alice, Emma
- Ordinateurs : PC-COMPTA1, PC-COMPTA2
- Groupes métiers dédiés

### Ressources partagées
- `commun`
- `comptabilite`
- dossier de partage pour le fond d’écran GPO

---

## Étapes réalisées

### 1. Création de l’environnement virtuel
- Création de la machine virtuelle serveur
- Préparation du poste client
- Installation de Windows Server et Windows 11

### 2. Déploiement du contrôleur de domaine
- Ajout du rôle **AD DS**
- Promotion du serveur en contrôleur de domaine
- Création du domaine **`keran.local`**

### 3. Organisation de l’Active Directory
- Création des unités d’organisation (OU)
- Création des groupes métiers
- Création des utilisateurs
- Création et classement des ordinateurs

### 4. Configuration réseau
- Paramétrage IP sur les machines
- Validation de la communication via **ping**
- Préparation du client pour la jonction au domaine

### 5. Mise en place des partages réseau
- Dossier **commun** accessible selon les droits définis
- Dossier **comptabilite** réservé aux utilisateurs autorisés
- Gestion combinée des **permissions de partage** et des **permissions NTFS**

### 6. Intégration des postes clients
- Configuration du poste client pour rejoindre le domaine
- Jonction au domaine **`keran.local`**
- Ouverture de session avec des comptes Active Directory

### 7. Déploiement des GPO
- **GPO de personnalisation** : déploiement d’un fond d’écran d’entreprise
- **GPO de sécurité** : blocage du Panneau de configuration et des Paramètres pour les utilisateurs ciblés

---

## Tests de validation

### Connectivité réseau
- Communication serveur / client validée
- Réponses **ping** fonctionnelles

### Domaine
- Jonction au domaine réussie
- Authentification via comptes AD confirmée

### Partages réseau
- Accès réussi au dossier **commun**
- Accès refusé au dossier **comptabilite** pour un utilisateur hors du groupe autorisé

### GPO
- Fond d’écran appliqué sur les postes ciblés
- Panneau de configuration bloqué pour les utilisateurs concernés
- Vérification qu’un autre service conserve l’accès si la stratégie ne s’applique pas à lui

---

## Difficultés rencontrées et points techniques traités

- Configuration IP et validation de la connectivité
- Ajustement des droits sur les partages réseau
- Gestion des permissions NTFS sur les dossiers sensibles
- Accès au chemin réseau du fond d’écran GPO
- Application et actualisation des stratégies via **gpupdate**

---

## Compétences développées

- Administration **Windows Server**
- Déploiement et gestion d’**Active Directory**
- Gestion des **utilisateurs**, **groupes** et **ordinateurs**
- Configuration **IP / DNS**
- Gestion des **partages réseau**
- Sécurité via **permissions de partage** et **NTFS**
- Déploiement de **GPO**
- Diagnostic et résolution de problèmes système et réseau

---

## Captures d’écran

### Création et installation
![Création VM](01-creation-vm.png)
![Installation Windows Server](02-installation-windows-server.png)
![Installation rôle AD DS](03-installation-role-ad-ds.png)
![Promotion contrôleur de domaine](04-promotion-controleur-domaine.png)

### Réseau et connectivité
![Configuration réseau serveur](05-configuration-reseau-serveur.png)
![Vérification ping serveur](06-verification-ping-serveur.png)

### Active Directory
![OU Active Directory](07-ou-active-directory.png)
![Utilisateurs et groupes](08-utilisateurs-et-groupes.png)
![Création utilisateurs](09-creation-utilisateurs.png)
![Création ordinateurs](10-creation-ordinateurs.png)

### Jonction au domaine
![Joindre le domaine](11-joindre-domaine.png)
![Jonction au domaine réussie](12-jonction-domaine-reussie.png)

### Partages réseau
![Accès aux partages](13-acces-partages-reseau.png)
![Partage dossier commun](14-partage-dossier-commun.png)
![Partage dossier comptabilité](15-partage-dossier-comptabilite.png)
![Accès refusé hors compta](16-acces-refuse-hors-compta.png)
![Accès commun réussi](17-acces-commun-reussi.png)

### GPO
![Création GPO fond d’écran](18-creation-gpo-fond-ecran.png)
![Sécurité partage fond d’écran](19-partage-fond-ecran.png)
![Fond d’écran appliqué](20-gpo-fond-ecran-appliquee.png)
![Création GPO blocage configuration](21-creation-gpo-blocage-config.png)
![Configuration GPO blocage](22-configuration-gpo-blocage.png)
![Résultat blocage panneau de configuration](23-resultat-blocage-panneau-config.png)
![Accès IT conservé](24-autorisation-it-panneau-config.png)

---

## Conclusion

Ce projet m’a permis de mettre en place une **infrastructure Active Directory cohérente et fonctionnelle**, avec une administration centralisée, des accès sécurisés, des postes intégrés au domaine et des stratégies de groupe opérationnelles.

Il illustre ma capacité à **concevoir, déployer, organiser, sécuriser et tester** un environnement Windows d’entreprise proche d’un contexte professionnel réel.
