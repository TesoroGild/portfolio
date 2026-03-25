---
title: MyUAAcademia
publishDate: 2026-03-25 00:00:00
img: /portfolio/assets/myua/logo.png
img_alt: MYUA's Logo
description: |
  Plateforme de gestion académique multi-rôles (étudiant, professeur, admin)
tags:
  - Design
  - Dev
link: https://
---

![Static Badge](https://img.shields.io/badge/React-gray?logo=react)
![Static Badge](https://img.shields.io/badge/Tailwind-gray?logo=Tailwindcss)
![Static Badge](https://img.shields.io/badge/Flowbite-gray?logo=react)
![Static Badge](https://img.shields.io/badge/React--Hook--Form-gray?logo=react)
![Static Badge](https://img.shields.io/badge/SQL_Server-gray?logo=microsoftsqlserver)

### À propos
MyUA Academia est une plateforme de gestion scolaire full-stack pensée pour centraliser les opérations d'un établissement d'enseignement supérieur. Le projet couvre l'intégralité du cycle de vie académique — de l'admission d'un étudiant jusqu'à la saisie des notes — en exposant trois espaces distincts selon le rôle de l'utilisateur connecté.

### Fonctionnalités Clés
##### Admission & Onboarding
<image src="/portfolio/assets/myua/admission1.png" width=400 center>
<image src="/portfolio/assets/myua/admission2.png" width=400 center>
<image src="/portfolio/assets/myua/admission3.png" width=400 center>
<image src="/portfolio/assets/myua/admission4.png" width=400 center>
<image src="/portfolio/assets/myua/admission5.png" width=400 center>
<image src="/portfolio/assets/myua/admission6.png" width=400 center>
<image src="/portfolio/assets/myua/admission7.png" width=400 center><br>
Formulaire d'admission public avec sélection de programmes (max 2), règles de complexité du mot de passe et upload de documents. Le flow complet couvre la vérification du dossier, le paiement des frais d'adhésion (120 $) et la confirmation par email.

##### Espace étudiant
<image src="/portfolio/assets/myua/sspace1.png" width=400 center><image src="/portfolio/assets/myua/sspace2.png" width=400 center>
<image src="/portfolio/assets/myua/sspace4.png" width=400 center><image src="/portfolio/assets/myua/sspace5.png" width=400 center>
<image src="/portfolio/assets/myua/sspace6.png" width=400 center><br>
* Inscription aux cours avec détection de conflits horaires et gestion du panier
* Facturation par session avec calcul dynamique (cours + frais fixes)
* Suivi du cheminement académique (cours réussis / en cours / à prendre)
* Bulletin de notes avec badges de mention colorés

##### Espace professeur
<image src="/portfolio/assets/myua/pspace1.png" width=500 center>
<image src="/portfolio/assets/myua/pspace2.png" width=500 center>
<image src="/portfolio/assets/myua/pspace3.png" width=500 center><br>
* Navigation drill-down Niveau → Programme → Cours → Étudiants inscrits
* Saisie des notes par select de mention (A+… E) avec import CSV et barre de progression
* Planning académique hebdomadaire et consultation des disponibilités de salles

##### Espace admin
<image src="/portfolio/assets/myua/aspace1.png" width=500 center>
<image src="/portfolio/assets/myua/aspace2.png" width=500 center>
<image src="/portfolio/assets/myua/aspace3.png" width=500 center>
<image src="/portfolio/assets/myua/aspace4.png" width=500 center><br>
* Gestion complète des employés : création, validation de dossiers, activation de comptes
* Système de contrats (postes ouverts) avec auto-remplissage lors de la création d'un employé
* Attribution des professeurs aux séances de cours
* Planning établissement filtré par professeur ou par salle


### Points forts techniques
- **Architecture RBAC** : Quatre rôles (étudiant, professeur, employé, admin) avec routing et composants conditionnels côté React, JWT côté API.
- **Modélisation des contrats** : Séparation entre le template de poste (Contracts) et l'instance individuelle (EmployeesContracts) — salaire négocié, dates réelles — reflétant une logique RH réaliste.
- **Gestion d'état asynchrone** : Résolution du problème N+1 (calcul de sous-totaux, notes) en retournant les données directement depuis les appels async plutôt que de lire le state React après set.
- **UX multi-rôles** : Un seul composant Sidebar et une seule page 404 contextuelle s'adaptent au rôle connecté sans duplication de code.

### Défis & Apprentissage
- **Flux de données imbriquées** : Gérer des entités fortement liées (programmes → cours → séances → étudiants → notes) a nécessité une réflexion poussée sur les endpoints et les jointures SQL pour éviter les appels en cascade côté front.
- **Séparation des responsabilités** : La distinction isValidated / isActivated sur les employés illustre un cas concret où deux états métier proches requièrent des champs séparés pour rester sémantiquement corrects.
- **Cohérence visuelle à grande échelle** : Plus de 30 pages avec des patterns réutilisables (drill-down, liste + panneau latéral, pills de filtre) conçus pour rester cohérents sans design system formel.

### Notes
<div style="color: #e53e3e; font-weight: 500; font-size: 0.9em; line-height: 1.5; border-left: 2px solid #e53e3e; padding-left: 15px; margin: 20px 0;">
  🔴 <strong>Initialisation des services</strong><br/>
  Cette application est hébergée sur des infrastructures <strong>Serverless</strong> (Vercel, Render et Neon). Pour optimiser les ressources, ces services entrent en "veille" après une période d'inactivité.<br/><br/>
  Lors du premier accès, un <strong>"Cold Start"</strong> d'environ 60 secondes peut survenir le temps de :
  <ul style="margin: 5px 0;">
    <li>1. Provisionner les containers d'exécution (Vercel/Render).</li>
    <li>2. Réactiver l'instance de la base de données PostgreSQL (Neon).</li>
    <li>3. Charger les dépendances et initialiser le runtime.</li>
  </ul><br/>
  Une fois réveillée, l'application répond instantanément. Merci de votre patience !
</div>

<div style="color: #3b82f6; font-weight: 500; font-size: 0.9em; line-height: 1.5; border-left: 2px solid #3b82f6; padding-left: 15px; margin: 20px 0;">
  🔵 <strong>Données de démonstration</strong><br/>
  L'application est peuplée avec des données fictives pour permettre une exploration complète des trois espaces sans création de compte.<br/><br/>

  Administrateurs :
  <ul style="margin: 5px 0;">
    <li>Emma : emp1 Emma1234-</li>
  </ul><br/>
  Professeurs :
  <ul style="margin: 5px 0;">
    <li>Curry : CURS14151988RN0 curry.</li>
    <li>Rihanna : FENR20351988PF0 Rihanna1234-</li>
  </ul><br/>
  Etudiants :
  <ul style="margin: 5px 0;">
    <li>Koffi : ABAK1628199914 ABAKbienvenido29.</li>
    <li>Wei : CHEW7758200122 Wei1234-.</li>
  </ul><br/>
</div>