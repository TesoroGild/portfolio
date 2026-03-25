---
title: MiandabouAccessoires
publishDate: 2026-03-01 00:00:00
img: /portfolio/assets/miandabou/mdb.png
img_alt: Miandabou's Logo
description: |
  E-commerce ERP
tags:
  - Design
  - Dev
  - User Testing
link: https://miandabou.vercel.app/home
---

![Static Badge](https://img.shields.io/badge/Angular-gray?logo=angular)
![Static Badge](https://img.shields.io/badge/Typescript-gray?logo=Typescript)
![Static Badge](https://img.shields.io/badge/Tailwind-gray?logo=Tailwindcss)
![Static Badge](https://img.shields.io/badge/i18n-gray?logo=i18next)
![Static Badge](https://img.shields.io/badge/Symfony-gray?logo=symfony)
![Static Badge](https://img.shields.io/badge/PHP-gray?logo=php)
![Static Badge](https://img.shields.io/badge/Composer-gray?logo=composer)
![Static Badge](https://img.shields.io/badge/Auth-JWT-blue?logo=jsonwebtokens)
![Static Badge](https://img.shields.io/badge/Docker-gray?logo=docker)
![Static Badge](https://img.shields.io/badge/PostgreSQL-gray?logo=PostgreSQL)

### À propos
Miandabou est une plateforme e-commerce full-stack conçue pour démontrer une maîtrise du cycle d'achat et de la gestion d'inventaire. L'objectif était de bâtir une architecture modulaire capable de gérer des rôles utilisateurs distincts et des flux de données complexes.

### Fonctionnalités Clés
##### Connexion
<image src="/portfolio/assets/miandabou/login.png" width=400 center>

##### Création de compte
<image src="/portfolio/assets/miandabou/signup1.png" width=400 center><image src="/portfolio/assets/miandabou/signup2.png" width=400 center>

##### Articles
- Pour les employés
<image src="/portfolio/assets/miandabou/stock.png" width=500 center>
- Pour les clients
<image src="/portfolio/assets/miandabou/items.png" width=500 center>

##### Panier
<image src="/portfolio/assets/miandabou/cart1.png" width=500 center>
<image src="/portfolio/assets/miandabou/cart2.png" width=500 center>

##### Facture
<image src="/portfolio/assets/miandabou/confirmation.png" width=500 center>
<image src="/portfolio/assets/miandabou/bill.png" width=500 center>

### Points forts techniques
- **Architecture** : Découplage complet entre une SPA (Angular) et une API REST (Symfony).

- **Sécurité** : Gestion des sessions via JWT en Symfony et protection des routes par AuthGuards côté Angular (RBAC).

- **Internationalisation & UI/UX** : L'application intègre un support i18n pour une interface multilingue. L'accent a été mis sur une expérience utilisateur fluide, de la simulation d'achat jusqu'à la génération d'une facture PDF.

### Défis & Apprentissage
- **Modélisation de données complexe** : Mise en œuvre de relations relationnelles avancées (Many-to-Many, One-to-Many) sous PostgreSQL pour gérer la flexibilité entre les articles, les  coupons et les avis utilisateurs.

- **Sécurité & Authentification** : Implémentation complète d'un système de jetons JWT (JSON Web Tokens) pour sécuriser les échanges entre le frontend Angular et l'API Symfony, couplé à des AuthGuards pour la gestion des accès par rôles (Client vs Employé).

- **Internationalisation (i18n)** : Architecture pensée pour le multilingue, permettant une adaptabilité de l'interface aux marchés internationaux.

- **DevOps & Déploiement** : Orchestration d'un environnement distribué avec Vercel (Frontend), Render (Backend API) et Neon (Base de données PostgreSQL Serverless), tout en isolant la couche de données via Docker pour le développement.

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


- **Flux de transaction simulé** : Afin de privilégier le développement de la logique métier (calculs de prix, gestion des taxes et génération de factures PDF), l'étape de paiement utilise un environnement de test (Mock Payment). Le système valide la structure des données sans traiter de transactions réelles, évitant ainsi des contraintes de conformité inutiles pour un prototype de portfolio.