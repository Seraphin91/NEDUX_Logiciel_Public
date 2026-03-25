# Nedux - Application Bureau (WPF)

> **Nedux** est une solution logicielle moderne de gestion de vie scolaire. Conçue avec une interface "Dark Mode" élégante et intuitive, l'application bureau s'adresse principalement au corps enseignant et à l'administration pour simplifier la gestion quotidienne (emplois du temps, agenda, communication, bulletins scolaires).

## À propos du projet

Ce dépôt contient le client lourd (Desktop) de l'écosystème Nedux, développé dans le cadre de notre 3ème année de BUT Informatique. Développé en **C# / WPF**, il met l'accent sur la productivité grâce à un design soigné (UI/UX), des composants personnalisés, une navigation fluide sans rechargement et une communication avec une API REST.

L'application gère différents rôles (Administrateur, Professeur) avec des vues et des droits adaptés à chacun, le tout sécurisé par un système d'authentification robuste.

---

## Fonctionnalités Principales

### Espace Administration
* **Tableau de bord interactif :** Raccourcis d'actions rapides, agenda de l'établissement et flux de notifications en temps réel.
* **Gestion des Élèves et des Classes :** Administration complète des effectifs, création et structuration des classes. Génération et gestion sécurisée des comptes permettant aux élèves d'accéder à leur application mobile Nedux.
* **Édition de Documents & Bulletins :** Génération automatique de relevés de notes et de bulletins scolaires au format PDF avec calcul des moyennes. Upload et gestion des documents administratifs liés aux dossiers des élèves.
* **Gestion des Absences et Retards :** Interface dédiée au suivi de l'assiduité. Permet de saisir, consulter et justifier les absences des élèves via un système de statuts et de pièces jointes.
* **Emploi du temps (EDT) Avancé :** * Vues journalière, hebdomadaire et mensuelle.
  * Création de cours avec système de vérification des conflits (Matière ➔ Professeur disponible ➔ Salle libre).
  * Duplication automatique de cours sur plusieurs semaines.
  * Calendrier Annuel avec affichage visuel par code couleur.
* **Gestion du Personnel (Professeurs & Ressources) :** Ajout/Modification des professeurs avec validation sécurisée des mots de passe par l'administrateur, assignation de matières (système de tags) et gestion des accès.
* **Vie Associative (Clubs) & Annonces :** Création et administration des clubs extrascolaires, et envoi de messages ciblés (Élèves, Professeurs, ou Tous).

### Espace Professeur
* **Agenda Numérique :** Création de devoirs assignables à plusieurs classes simultanément (système de tags multi-sélection). Affichage intelligent scindé en deux ("Devoirs en cours" et historique).
* **Partage de Ressources :** Upload de fichiers de cours ou d'exercices directement accessibles par les élèves sur leur application mobile.
* **Consultation EDT :** Accès en lecture seule à son emploi du temps personnel avec détails interactifs des cours.
* **Saisie des Notes :** Interface d'évaluation des élèves.
* **Communication :** Réception et lecture des annonces de l'administration.

---

## Interface et Design (UI/UX)

Une attention toute particulière a été portée à l'interface utilisateur pour s'éloigner des logiciels de gestion traditionnels austères :
* **Thème Sombre (Dark Mode) natif :** Couleurs dominantes bleu nuit (`#13151D`) et accents Cyan (`#00BCD4`).
* **Composants Personnalisés :** * `NeduxComboBox` (Menus déroulants stylisés).
  * Modales superposées (Overlays) avec effets de transparence.
  * Boutons d'actions dynamiques (Hover, clic).
  * Boîtes de dialogue de confirmation sur mesure (`ConfirmDialog`).
* **Système de Tags :** Utilisation intensive de badges visuels pour l'assignation de classes ou de matières.

---

## Technologies Utilisées

* **Langage :** C# (.NET)
* **Framework UI :** WPF (Windows Presentation Foundation) / XAML
* **Architecture :** Pattern orienté MVVM / Services (Séparation des Vues, Modèles et Services d'accès aux données).
* **Communication Réseau :** Consommation d'une API REST externe via `HttpClient`.
* **Persistance des Données :** Base de données MySQL via l'API (avec architecture `WAPI` de mock intégrée pour garantir l'autonomie lors des phases de tests locaux).

---

## Structure du Projet

```text
NeduxApp/
├── Models/           # Modèles de données (TeacherItem, AssignmentItem, etc.)
├── Services/         # Logique métier et appels API (EDTWAPI, AgendaProfWAPI, etc.)
├── views/            # Fichiers XAML et Code-Behind
│   ├── Admin/        # (EDTAdminView, TeachersView...)
│   ├── Prof/         # (DashboardProfView, AgendaProfView, EDTProfView...)
│   └── Shared/       # Composants partagés (ConfirmDialog...)
└── ressources/       # Images, logos, polices
```
## Licence et Droits d'auteur

**© 2026 Nedux - Tous droits réservés.**

Ce projet est une propriété intellectuelle fermée et propriétaire. L'intégralité du code source, de l'architecture, de la logique métier et du design (UI/UX) appartient exclusivement à ses créateurs et à l'équipe de développement.

⚠️ **Avertissement strict :** Ce code n'est **pas** open-source. Il est strictement interdit de copier, reproduire, distribuer, modifier ou utiliser ce code (en partie ou dans sa totalité) à des fins commerciales, éducatives ou personnelles sans une autorisation écrite explicite. Ce logiciel est en cours de développement et a pour vocation d'être un produit commercialisé dans sa version finale.
