# 🎓 Nedux - Application Bureau (WPF)

> **Nedux** est une solution logicielle moderne de gestion de vie scolaire. Conçue avec une interface "Dark Mode" élégante et intuitive, l'application bureau s'adresse principalement au corps enseignant et à l'administration pour simplifier la gestion quotidienne (emplois du temps, agenda, communication).

## 🌟 À propos du projet

Ce dépôt contient le client lourd (Desktop) de l'écosystème Nedux. Développé en **C# / WPF**, il met l'accent sur la productivité grâce à un design soigné (UI/UX), des composants personnalisés et une navigation fluide sans rechargement.

L'application gère différents rôles (Administrateur, Professeur) avec des vues et des droits adaptés à chacun.

---

## 🚀 Fonctionnalités Principales

### 🛡️ Espace Administration
* **Tableau de bord interactif :** Raccourcis d'actions rapides, alertes récentes et flux de notifications.
* **Gestion des Élèves et des Classes :** Administration complète des effectifs, création et structuration des classes. Génération et gestion des comptes de connexion permettant aux élèves d'accéder à leur application mobile Nedux.
* **Gestion des Absences :** Interface dédiée au suivi de l'assiduité. Permet de saisir, consulter et justifier (ou non) les absences des élèves en temps réel.
* **Emploi du temps (EDT) Avancé :** * Vues journalière, hebdomadaire et mensuelle.
  * Création de cours avec système de "cascade" (Matière ➔ Professeur disponible ➔ Salle libre).
  * Duplication automatique de cours sur plusieurs semaines.
  * **Calendrier Annuel :** Planification globale (Vacances, Conseils de classe, Examens) avec un affichage visuel par code couleur.
* **Gestion du Personnel (Professeurs & Ressources) :** Ajout/Modification sécurisée des professeurs, assignation de matières (système de tags) et gestion des accès.
* **Vie Associative (Clubs) :** Création et administration des différents clubs et activités extrascolaires proposés par l'établissement.
* **Annonces :** Envoi de messages ciblés (Élèves, Professeurs, ou Tous).

### 👨‍🏫 Espace Professeur
* **Agenda Numérique :** * Création de devoirs assignables à plusieurs classes simultanément (système de tags multi-sélection).
  * Affichage intelligent scindé en deux : "Devoirs en cours" (mis en évidence) et "Précédents devoirs" (historique grisé).
* **Consultation EDT :** Accès en lecture seule à son emploi du temps personnel avec détails interactifs des cours.
* **Communication :** Réception et lecture des annonces de l'administration.
---

## 🎨 Interface et Design (UI/UX)

Une attention toute particulière a été portée à l'interface utilisateur pour s'éloigner des logiciels de gestion traditionnels austères :
* **Thème Sombre (Dark Mode) natif :** Couleurs dominantes bleu nuit (`#13151D`) et accents Cyan (`#00BCD4`).
* **Composants Personnalisés :** * `NeduxComboBox` (Menus déroulants stylisés).
  * Modales superposées (Overlays) avec effets de transparence.
  * Boutons d'actions dynamiques (Hover, clic).
  * Boîtes de dialogue de confirmation sur mesure (`ConfirmDialog`).
* **Système de Tags :** Utilisation intensive de badges visuels pour l'assignation de classes ou de matières.

---

## 💻 Technologies Utilisées

* **Langage :** C# (.NET)
* **Framework UI :** WPF (Windows Presentation Foundation) / XAML
* **Architecture :** Pattern orienté MVVM / Services (Séparation des Vues, Modèles et Services d'accès aux données).
* **Stockage (Actuel) :** Interface `WAPI` (Fake Database en mémoire) prête à être connectée à une véritable API REST.

---

## 📁 Structure du Projet

```text
NeduxApp/
├── Models/           # Modèles de données (TeacherItem, AssignmentItem, etc.)
├── Services/         # Logique métier et appels API (EDTWAPI, AgendaProfWAPI, etc.)
├── views/            # Fichiers XAML et Code-Behind
│   ├── Admin/        # (EDTAdminView, TeachersView...)
│   ├── Prof/         # (DashboardProfView, AgendaProfView, EDTProfView...)
│   └── Shared/       # Composants partagés (ConfirmDialog...)
└── ressources/       # Images, logos, polices
