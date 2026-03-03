---
title: MiandabouAccessoires
publishDate: 2026-03-01 00:00:00
img: /portfolio/assets/mdb.png
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
##### Connection
<image src="/portfolio/assets/login.png" width=400 center>

##### Création de compte
<image src="/portfolio/assets/signup1.png" width=400 center><image src="/portfolio/assets/signup2.png" width=400 center>

##### Articles
- Pour les employés
<image src="/portfolio/assets/stock.png" width=500 center>
- Pour les clients
<image src="/portfolio/assets/items.png" width=500 center>

##### Panier
<image src="/portfolio/assets/cart1.png" width=500 center>
<image src="/portfolio/assets/cart2.png" width=500 center>

##### Facture
<image src="/portfolio/assets/confirmation.png" width=500 center>
<image src="/portfolio/assets/bill.png" width=500 center>

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
- **Flux de transaction simulé** : Afin de privilégier le développement de la logique métier (calculs de prix, gestion des taxes et génération de factures PDF), l'étape de paiement utilise un environnement de test (Mock Payment). Le système valide la structure des données sans traiter de transactions réelles, évitant ainsi des contraintes de conformité inutiles pour un prototype de portfolio.