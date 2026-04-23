# STRUCTURE COMPLÈTE — SITE E-COMMERCE FRANCE 2026

> **Document de référence** pour la création d’un site de vente en ligne conforme à la réglementation française en vigueur au 23 avril 2026.
> Couvre : architecture technique, pages obligatoires, conformité juridique, SEO, paiement, logistique, marketing et suivi de performance.

-----

## TABLE DES MATIÈRES

1. [Architecture globale du site](#1-architecture-globale-du-site)
1. [Pages obligatoires & conformité juridique](#2-pages-obligatoires--conformité-juridique)
1. [Tunnel d’achat & processus de commande](#3-tunnel-dachat--processus-de-commande)
1. [RGPD & gestion des données personnelles](#4-rgpd--gestion-des-données-personnelles)
1. [Cookies & CMP (Consent Management Platform)](#5-cookies--cmp-consent-management-platform)
1. [Accessibilité numérique (RGAA / EAA)](#6-accessibilité-numérique-rgaa--eaa)
1. [Paiement & sécurité des transactions](#7-paiement--sécurité-des-transactions)
1. [Facturation & obligations fiscales](#8-facturation--obligations-fiscales)
1. [Logistique, livraison & suivi](#9-logistique-livraison--suivi)
1. [Obligations environnementales (Loi AGEC)](#10-obligations-environnementales-loi-agec)
1. [DSA (Digital Services Act) & règlement Omnibus](#11-dsa-digital-services-act--règlement-omnibus)
1. [SEO & performance technique](#12-seo--performance-technique)
1. [Marketing & acquisition](#13-marketing--acquisition)
1. [Back-office & administration](#14-back-office--administration)
1. [Stack technique recommandée](#15-stack-technique-recommandée)
1. [Checklist de lancement](#16-checklist-de-lancement)
1. [Sanctions encourues — synthèse](#17-sanctions-encourues--synthèse)

-----

## 1. ARCHITECTURE GLOBALE DU SITE

### 1.1 Arborescence de navigation

```
/                           → Page d'accueil
├── /boutique               → Catalogue produits
│   ├── /categorie-1        → Page catégorie
│   │   └── /produit-slug   → Fiche produit
│   └── /categorie-2
├── /panier                 → Panier
├── /commande               → Tunnel de commande (checkout)
│   ├── /identification     → Connexion / Création de compte / Invité
│   ├── /livraison          → Choix adresse et mode de livraison
│   ├── /paiement           → Sélection du moyen de paiement
│   └── /confirmation       → Récapitulatif avant validation
├── /confirmation-commande  → Page post-paiement (merci)
├── /mon-compte             → Espace client
│   ├── /commandes          → Historique des commandes
│   ├── /retractation       → Formulaire de rétractation en ligne ⚠️ NOUVEAU 2026
│   ├── /retours            → Suivi des retours
│   ├── /adresses           → Gestion des adresses
│   ├── /donnees-personnelles → Droits RGPD (accès, rectification, suppression)
│   └── /factures           → Téléchargement des factures
├── /pages
│   ├── /mentions-legales           → OBLIGATOIRE
│   ├── /cgv                        → OBLIGATOIRE (B2C)
│   ├── /politique-confidentialite  → OBLIGATOIRE (RGPD)
│   ├── /politique-cookies          → OBLIGATOIRE
│   ├── /accessibilite              → OBLIGATOIRE (déclaration RGAA)
│   ├── /mediation                  → OBLIGATOIRE
│   ├── /livraison-et-retours       → Recommandé
│   ├── /faq                        → Recommandé
│   └── /a-propos                   → Recommandé
├── /blog                   → Contenus éditoriaux / SEO
├── /contact                → Formulaire de contact
├── /plan-du-site           → Sitemap HTML
├── /sitemap.xml            → Sitemap XML (moteurs de recherche)
└── /robots.txt             → Instructions crawlers
```

### 1.2 Pages techniques (non visibles utilisateur)

```
/404                        → Page erreur personnalisée
/500                        → Page erreur serveur
/maintenance                → Page maintenance planifiée
/desabonnement              → Lien de désinscription newsletter
/webhooks/*                 → Endpoints paiement / logistique
```

-----

## 2. PAGES OBLIGATOIRES & CONFORMITÉ JURIDIQUE

### 2.1 Mentions légales — OBLIGATOIRE

**Base légale** : Loi LCEN du 21 juin 2004, art. 6-III-1.
**Sanction** : jusqu’à 75 000 € (personne physique) / 375 000 € (personne morale) + 1 an d’emprisonnement.

**Contenu obligatoire :**

- Identité de l’éditeur : nom/prénom (EI) ou dénomination sociale, forme juridique, montant du capital social
- Adresse du siège social
- Numéro d’immatriculation RCS ou numéro SIREN/SIRET
- Numéro de TVA intracommunautaire
- Email et numéro de téléphone de contact
- Nom du directeur de la publication
- Identité de l’hébergeur : nom, adresse, téléphone
- Si activité réglementée : nom et adresse de l’autorité ayant délivré l’autorisation
- Numéro de déclaration CNIL (ou mention du DPO)

### 2.2 Conditions Générales de Vente (CGV) — OBLIGATOIRE en B2C

**Base légale** : Code de la consommation, articles L111-1 et suivants.
**Sanction** : 3 000 € (EI) / 15 000 € (société) pour défaut d’information précontractuelle.

**Contenu obligatoire :**

- Caractéristiques essentielles des biens/services
- Prix TTC (incluant taxes et frais de livraison)
- Modalités de paiement acceptées
- Conditions et délai de livraison
- Droit de rétractation : délai de 14 jours, conditions, exceptions
- **⚠️ NOUVEAU au 19 juin 2026** : mention de la fonctionnalité de rétractation en ligne (ordonnance n° 2026-2 du 5 janvier 2026)
- Garantie légale de conformité (2 ans minimum)
- Garantie des vices cachés
- Garantie commerciale éventuelle et SAV
- Coordonnées du médiateur de la consommation (obligatoire depuis 2016)
- Durée du contrat et conditions de résiliation (si applicable)
- Conditions de caution ou garantie (si applicable)
- Droit applicable et juridiction compétente

### 2.3 Politique de confidentialité — OBLIGATOIRE

**Base légale** : RGPD (Règlement UE 2016/679), Loi Informatique et Libertés.

Voir section 4 pour le détail complet.

### 2.4 Politique de cookies — OBLIGATOIRE

**Base légale** : Directive ePrivacy, recommandations CNIL.

Voir section 5 pour le détail complet.

### 2.5 Déclaration d’accessibilité — OBLIGATOIRE (si concerné)

**Base légale** : RGAA 4.1, Directive EAA 2019/882.

Voir section 6 pour le détail complet.

### 2.6 Page médiation — OBLIGATOIRE

**Base légale** : Code de la consommation, art. L612-1 et suivants (obligatoire depuis le 1er janvier 2016).

**Contenu obligatoire :**

- Nom du médiateur de la consommation désigné
- Coordonnées complètes (adresse, site web, email)
- Modalités de saisine
- Lien vers la plateforme européenne de RLL : https://ec.europa.eu/consumers/odr

-----

## 3. TUNNEL D’ACHAT & PROCESSUS DE COMMANDE

### 3.1 Processus en 3 étapes obligatoires (Code de la consommation)

1. **Détail et récapitulatif** : affichage complet de la commande avec prix total TTC (produits + livraison + taxes)
1. **Possibilité de correction** : le client doit pouvoir modifier sa commande avant validation
1. **Confirmation explicite** : bouton de validation avec mention « Commande avec obligation de paiement » ou formulation équivalente sans ambiguïté

### 3.2 Informations pré-contractuelles à afficher avant validation

- Absence ou existence du droit de rétractation
- Frais de retour à la charge du consommateur (si applicable)
- Adresse de retour physique
- Délai de livraison estimé
- Moyens de paiement acceptés
- Restrictions de livraison éventuelles

### 3.3 Post-commande

- Confirmation de commande par email (support durable) contenant : résumé, numéro de commande, date, conditions de rétractation, lien vers le formulaire de rétractation en ligne
- Facture conforme (voir section 8)
- Notification d’expédition avec numéro de suivi

### 3.4 Rétractation en ligne — ⚠️ NOUVEAU 19 JUIN 2026

**Base légale** : Ordonnance n° 2026-2 et décret n° 2026-3 du 5 janvier 2026.

Le site DOIT proposer une fonctionnalité permettant au consommateur d’exercer son droit de rétractation **directement en ligne**, accessible pendant toute la durée du délai légal (14 jours). Le professionnel doit adresser un accusé de réception sur support durable, précisant le contenu de la demande ainsi que la date et l’heure d’envoi.

**Implémentation :**

- Page dédiée `/mon-compte/retractation`
- Formulaire en ligne identifiant la commande et les articles concernés
- Accusé de réception automatique par email
- Tableau de suivi du statut de la rétractation dans l’espace client

-----

## 4. RGPD & GESTION DES DONNÉES PERSONNELLES

### 4.1 Politique de confidentialité — contenu obligatoire

- Identité et coordonnées du responsable de traitement
- Coordonnées du DPO (si applicable)
- Finalités de chaque traitement de données
- Base légale de chaque traitement (consentement, contrat, obligation légale, intérêt légitime)
- Catégories de données collectées
- Destinataires des données (sous-traitants, partenaires, transferts hors UE)
- Durée de conservation par catégorie de données
- Droits des personnes : accès, rectification, suppression, portabilité, opposition, limitation
- Droit d’introduire une réclamation auprès de la CNIL
- Existence éventuelle de profilage ou de prise de décision automatisée

### 4.2 Fonctionnalités RGPD à implémenter

- **Consentement explicite** : opt-in actif (case non pré-cochée) pour la newsletter, les communications marketing
- **Centre de préférences** : page dans l’espace client pour gérer les consentements
- **Droit d’accès** : export des données personnelles au format lisible (JSON, CSV ou PDF)
- **Droit de suppression** : procédure de suppression de compte avec confirmation
- **Droit de portabilité** : téléchargement des données dans un format structuré
- **Registre des traitements** : document interne (non public mais obligatoire)
- **Notification de violation** : procédure interne (72h pour notifier la CNIL)

### 4.3 Durées de conservation recommandées (CNIL)

|Type de données                |Durée                              |
|-------------------------------|-----------------------------------|
|Données clients actifs         |Durée de la relation commerciale   |
|Données après dernière activité|3 ans max (prospection commerciale)|
|Données de facturation         |10 ans (obligation comptable)      |
|Logs de connexion              |1 an (obligation légale)           |
|Cookies analytics              |25 mois max                        |
|Données de paiement (CB)       |Durée de la transaction uniquement |

-----

## 5. COOKIES & CMP (CONSENT MANAGEMENT PLATFORM)

### 5.1 Obligations légales

**Base légale** : Art. 82 de la loi Informatique et Libertés, recommandations CNIL.
**Sanction** : jusqu’à 4 % du CA mondial annuel (RGPD).

**Règles clés :**

- Bandeau de consentement affiché **avant** tout dépôt de cookie non essentiel
- Bouton « Refuser » aussi visible et accessible que le bouton « Accepter » (la CNIL a sanctionné des entreprises pour des boutons « Refuser » cachés ou grisés)
- Consentement valable 13 mois maximum, puis re-demande obligatoire
- Le refus ne doit pas empêcher la navigation sur le site
- Conservation de la preuve du consentement

### 5.2 Cookies exemptés de consentement

- Cookie de session (panier, authentification)
- Cookie de choix de langue
- Cookie de mémorisation du consentement cookies
- Analytics anonymisés et configurés pour l’exemption CNIL (ex. : Matomo sans tracking cross-site)

### 5.3 Solutions CMP recommandées

- **Axeptio** — certification CNIL, approche UX innovante, adapté au marché français
- **Didomi** — fonctionnalités avancées, plutôt grands comptes
- **Tarteaucitron** — open source, gratuit, très utilisé en France
- **OneTrust** — suite complète, entreprises internationales

### 5.4 Politique de cookies — contenu obligatoire

- Liste exhaustive des cookies déposés (nom, finalité, durée, émetteur)
- Distinction cookies essentiels / analytics / publicitaires / réseaux sociaux
- Procédure de modification ou retrait du consentement
- Lien vers la politique de confidentialité

-----

## 6. ACCESSIBILITÉ NUMÉRIQUE (RGAA / EAA)

### 6.1 Qui est concerné ?

**European Accessibility Act (EAA)** — Directive 2019/882, applicable depuis le 28 juin 2025 :

- Toute entreprise e-commerce **> 10 salariés** OU **> 2 M€ de CA annuel**
- Les micro-entreprises (< 10 salariés ET < 2 M€ CA) sont exemptées
- Services existants avant le 28 juin 2025 : délai jusqu’au 28 juin 2030
- Services lancés après le 28 juin 2025 : conformité immédiate

**Sanctions :**

- DGCCRF : jusqu’à 7 500 € (personne morale) + astreinte de 3 000 €/jour (plafond 300 000 €)
- ARCOM : jusqu’à 50 000 € par service non conforme (renouvelable tous les 6 mois)
- Absence de déclaration d’accessibilité : jusqu’à 25 000 €

### 6.2 Référentiel applicable

- **RGAA 4.1.2** (version en vigueur) basé sur WCAG 2.1 niveau AA — 106 critères
- **RGAA 5** prévu fin 2026, intégrera WCAG 2.2

### 6.3 Obligations techniques clés

- Alternatives textuelles sur toutes les images (attributs `alt`)
- Contraste de couleurs suffisant (ratio minimum 4.5:1 pour le texte normal)
- Navigation complète au clavier
- Structure sémantique HTML correcte (headings, landmarks, listes)
- Sous-titrage des vidéos, transcriptions audio
- Formulaires accessibles avec labels associés et messages d’erreur explicites
- Documents téléchargeables (PDF) accessibles
- Compatibilité avec les technologies d’assistance (lecteurs d’écran)

### 6.4 Obligations déclaratives

- **Mention d’accessibilité** visible sur chaque page (footer) : « Accessibilité : conforme / partiellement conforme / non conforme »
- **Déclaration d’accessibilité** publiée : niveau de conformité, date d’audit, dérogations, contact
- **Schéma pluriannuel** (plan d’actions sur 3 ans) : publié et mis à jour annuellement

-----

## 7. PAIEMENT & SÉCURITÉ DES TRANSACTIONS

### 7.1 Obligations de sécurité

- **HTTPS obligatoire** sur l’ensemble du site (certificat SSL/TLS)
- **Conformité PCI DSS** pour le traitement des données de carte bancaire (en 2026, cette norme est devenue incontournable)
- **Authentification forte (SCA)** : 3D Secure 2 obligatoire sur les paiements par carte dans l’EEE (DSP2)
- Ne jamais stocker les numéros de carte côté serveur (déléguer au PSP)

### 7.2 Moyens de paiement recommandés

|Moyen                                |Obligatoire ?          |Notes                               |
|-------------------------------------|-----------------------|------------------------------------|
|Carte bancaire (CB, Visa, Mastercard)|Non, mais indispensable|~80% des paiements en France        |
|PayPal                               |Non                    |Standard international              |
|Apple Pay / Google Pay               |Non                    |En forte croissance                 |
|Virement bancaire                    |Non                    |Utile pour le B2B                   |
|Paiement en 3/4x                     |Non                    |Soumis au crédit conso si > 90 jours|
|Chèque                               |Non                    |En déclin                           |

### 7.3 Mentions obligatoires

- Afficher les moyens de paiement acceptés dès le début du processus de commande
- Indiquer clairement les frais de paiement éventuels (interdit de facturer un surcoût pour l’utilisation d’un moyen de paiement spécifique en B2C — Directive Services de Paiement)

### 7.4 PSP (Payment Service Providers) courants en France

- Stripe
- Mollie
- PayPlug (français)
- Adyen
- PayPal Commerce Platform

-----

## 8. FACTURATION & OBLIGATIONS FISCALES

### 8.1 Facturation électronique — ⚠️ RÉFORME MAJEURE 2026

**Base légale** : Loi de finances, art. 289 bis CGI.

**Calendrier :**

- **1er sept. 2026** — Réception obligatoire pour TOUTES les entreprises
- **1er sept. 2026** — Émission obligatoire pour les grandes entreprises et ETI
- **1er sept. 2027** — Émission obligatoire pour les PME et micro-entreprises

**E-invoicing (B2B)** : factures échangées entre assujettis TVA via une plateforme agréée (PA).
**E-reporting (B2C, export)** : transmission des données de transaction et de paiement à l’administration.

**Formats structurés obligatoires** : Factur-X (PDF + XML), UBL, CII.

**Nouvelles mentions obligatoires sur les factures (sept. 2026) :**

- Catégorie de l’opération (livraison de bien / prestation de service / mixte)
- Mention de l’option de paiement de la TVA sur les débits (si applicable)
- Adresse complète de livraison (si différente de l’adresse de facturation)
- Numéro SIREN du client

**Sanctions** : 15 € par facture non conforme (plafond 15 000 €/an) ; 250 € par donnée e-reporting manquante (plafond 15 000 €/an).

### 8.2 Mentions classiques obligatoires sur toute facture

- Date d’émission
- Numérotation chronologique unique
- Identité complète du vendeur (SIREN, RCS, adresse, TVA intracommunautaire)
- Identité complète de l’acheteur
- Désignation des produits/services, quantité, prix unitaire HT
- Taux de TVA applicable, montant HT, montant TVA, montant TTC
- Date de livraison ou d’exécution du service
- Conditions de paiement et date d’échéance
- Pénalités de retard et indemnité forfaitaire de recouvrement (40 €) — pour le B2B

### 8.3 TVA — régimes applicables

- **Franchise en base de TVA** : micro-entreprises sous les seuils (36 800 € services / 91 900 € vente) — pas de collecte de TVA
- **Régime réel** : collecte et déclaration obligatoires
- **TVA e-commerce UE (OSS/IOSS)** : guichet unique pour les ventes intra-UE à distance aux consommateurs (seuil 10 000 €)

### 8.4 Douanes — ⚠️ NOUVEAU 1er JUILLET 2026

À compter du 1er juillet 2026, l’UE imposera des droits de douane fixes de 3 € sur tous les colis importés d’une valeur inférieure à 150 €, mettant fin à l’exonération des petits colis.

-----

## 9. LOGISTIQUE, LIVRAISON & SUIVI

### 9.1 Obligations légales

- **Date de livraison** : le vendeur doit indiquer une date ou un délai de livraison avant la commande
- **Délai maximum** : à défaut de mention, le Code de la consommation impose la livraison dans les 30 jours suivant la commande
- **Retard de livraison** : le consommateur peut annuler la commande si le vendeur ne livre pas après une mise en demeure restée infructueuse (dépassement raisonnable ou date essentielle non respectée)
- **Traçabilité des envois** : numéro de suivi recommandé (fortement attendu)
- **Transfert de risque** : les risques pèsent sur le vendeur jusqu’à la prise de possession par le consommateur (B2C)

### 9.2 Page « Livraison et retours » — contenu recommandé

- Zones de livraison (France métropolitaine, DOM-TOM, international)
- Modes de livraison disponibles (domicile, point relais, click & collect)
- Tarifs de livraison par mode et par zone
- Délais de livraison estimés par mode
- Politique de retour : conditions, délai, frais de retour
- Procédure de réclamation en cas de colis endommagé ou manquant

### 9.3 Transporteurs courants en France

- Colissimo / Chronopost (La Poste)
- Mondial Relay
- Relais Colis
- DPD / GLS
- UPS / FedEx / DHL (international)

-----

## 10. OBLIGATIONS ENVIRONNEMENTALES (LOI AGEC)

### 10.1 Calendrier 2026

**Base légale** : Loi n° 2020-105 du 10 février 2020 (Anti-Gaspillage pour une Économie Circulaire).

|Date          |Obligation                                                                                       |
|--------------|-------------------------------------------------------------------------------------------------|
|1er janv. 2026|Extension de l’indice de durabilité (aspirateurs, TV, PC portables)                              |
|1er mars 2026 |Affichage environnemental obligatoire pour les produits textiles                                 |
|1er avril 2026|Plateformes de vente en ligne : vérifier l’adhésion REP des vendeurs, suspendre les non-conformes|
|1er juin 2026 |Bonus-malus écoconception dans toutes les filières REP                                           |
|1er sept. 2026|Interdiction de certains emballages plastiques (cosmétiques, hygiène)                            |

### 10.2 Obligations permanentes pour un e-commerce

- **Indice de réparabilité / durabilité** : affichage obligatoire sur les fiches produits pour les catégories concernées (smartphones, ordinateurs, TV, lave-linge, etc.)
- **Affichage environnemental** : score environnemental sur les produits textiles et électroniques
- **Information sur les qualités et caractéristiques environnementales** : présence de substances dangereuses, recyclabilité, incorporation de matière recyclée
- **Interdiction de destruction des invendus** : obligation de don, recyclage ou valorisation
- **REP (Responsabilité Élargie du Producteur)** : adhésion à un éco-organisme pour les filières concernées (emballages, DEEE, textile, jouets, bricolage, etc.)
- **Signalétique de tri (Triman + Info-tri)** : obligatoire sur les produits et emballages
- **Interdiction du greenwashing** : ne pas utiliser les termes « biodégradable », « respectueux de l’environnement » sans justification vérifiable

### 10.3 Green Claims Directive (à anticiper)

La directive européenne sur les allégations environnementales renforcera les obligations de justification des claims « éco-responsable », « vert », « durable », etc. Toute allégation devra s’appuyer sur des preuves scientifiques vérifiables.

-----

## 11. DSA (DIGITAL SERVICES ACT) & RÈGLEMENT OMNIBUS

### 11.1 DSA — applicable depuis le 17 février 2024

**Base légale** : Règlement (UE) 2022/2065.

Si le site fait de la place de marché (marketplace) ou héberge du contenu tiers :

- Mécanisme de signalement des contenus illicites
- Transparence sur les recommandations algorithmiques
- Obligation de traçabilité des vendeurs tiers (identité, coordonnées, numéro d’identification)
- Point de contact unique pour les autorités
- Transparence sur la publicité en ligne (identité de l’annonceur, paramètres de ciblage)

### 11.2 Directive Omnibus (transposée en droit français)

- **Avis consommateurs** : si le site affiche des avis, il doit indiquer s’ils sont vérifiés et comment, et ne doit pas publier de faux avis
- **Réductions de prix** : obligation d’afficher le prix antérieur le plus bas pratiqué au cours des 30 jours précédant la réduction
- **Classement des résultats** : si le site classe les produits, les critères de classement doivent être accessibles
- **Personnalisation des prix** : informer le consommateur si le prix est personnalisé sur la base de profilage

### 11.3 Dark patterns — interdiction renforcée

Le RIA (Règlement européen sur l’IA), pleinement applicable en 2026, renforce l’interdiction des techniques de manipulation de l’interface :

- Cases pré-cochées interdites
- Processus de résiliation aussi simple que l’abonnement
- Pas de culpabilisation lors du refus (« confirshaming »)
- Pas de fausse urgence ou fausse rareté trompeuse

-----

## 12. SEO & PERFORMANCE TECHNIQUE

### 12.1 Fondamentaux techniques

- **Sitemap XML** dynamique (`/sitemap.xml`) soumis à Google Search Console et Bing Webmaster Tools
- **Robots.txt** configuré pour bloquer les pages non indexables (panier, checkout, compte)
- **Balisage sémantique** : données structurées Schema.org (Product, Offer, BreadcrumbList, FAQPage, Organization, Review)
- **Balises canoniques** pour éviter le contenu dupliqué (variantes de produits, pagination)
- **Redirections 301** pour toute URL modifiée
- **Hreflang** si site multilingue

### 12.2 Performance (Core Web Vitals)

|Métrique                       |Cible  |
|-------------------------------|-------|
|LCP (Largest Contentful Paint) |< 2,5s |
|INP (Interaction to Next Paint)|< 200ms|
|CLS (Cumulative Layout Shift)  |< 0,1  |

**Optimisations :**

- Images en format WebP/AVIF avec lazy loading
- Minification CSS/JS
- CDN pour les assets statiques
- Compression Brotli/Gzip
- Mise en cache côté serveur et navigateur

### 12.3 SEO on-page pour les fiches produits

- Title unique < 60 caractères
- Meta description unique < 155 caractères
- URL slug lisible et optimisée
- H1 unique (nom du produit)
- Description produit originale (pas de copier-coller fournisseur)
- Images optimisées avec attributs `alt` descriptifs
- Fil d’Ariane (breadcrumb) avec balisage Schema.org
- Avis clients avec balisage `Review` / `AggregateRating`

-----

## 13. MARKETING & ACQUISITION

### 13.1 Email marketing — obligations RGPD

- **Opt-in** obligatoire (B2C) : consentement actif avant l’envoi de newsletters
- **Exception « soft opt-in »** : un client existant peut recevoir des emails sur des produits similaires, avec possibilité de se désinscrire
- **Lien de désinscription** fonctionnel dans chaque email
- **Identification de l’expéditeur** claire
- **Objet non trompeur**

### 13.2 Publicité en ligne

- **Mentions « Publicité » ou « Annonce »** obligatoires sur tout contenu sponsorisé
- **Influenceurs** : loi du 9 juin 2023 — mentions obligatoires (#pub, #publicité), interdiction de promouvoir certains produits (chirurgie esthétique, paris, etc.)
- **Remarketing/retargeting** : soumis au consentement cookies

### 13.3 Réseaux sociaux

- Boutons de partage social soumis au consentement cookies (ils déposent des traceurs)
- Liens vers les comptes sociaux de la marque
- Pixels de tracking (Meta, TikTok, etc.) soumis au consentement

### 13.4 Programme de fidélité / parrainage

- CGU spécifiques obligatoires
- Règles claires sur l’accumulation et l’utilisation des points
- Conformité RGPD sur le traitement des données associées

-----

## 14. BACK-OFFICE & ADMINISTRATION

### 14.1 Gestion des commandes

- Tableau de bord des commandes (statuts : en attente, payée, en préparation, expédiée, livrée, retournée, remboursée, rétractée)
- Gestion des retours et rétractations avec workflow automatisé
- Gestion des remboursements (délai légal : 14 jours après rétractation)
- Archivage des commandes (10 ans pour les obligations comptables)

### 14.2 Gestion du catalogue

- CRUD produits (création, modification, suppression, archivage)
- Gestion des variantes (taille, couleur, etc.)
- Gestion des stocks avec alertes de rupture
- Import/export CSV ou API pour les mises à jour massives
- Gestion des catégories et tags

### 14.3 Gestion des clients

- Base clients conforme RGPD (durées de conservation, droits d’accès)
- Segmentation pour le marketing
- Historique des interactions (commandes, tickets SAV, retours)

### 14.4 Outils d’analyse

- Dashboard de vente (CA, panier moyen, taux de conversion)
- Analytics web (Matomo recommandé pour la conformité CNIL sans consentement)
- Suivi des abandons de panier
- Rapports de performance par canal d’acquisition

-----

## 15. STACK TECHNIQUE RECOMMANDÉE

### 15.1 Options CMS / Framework e-commerce

|Solution                   |Type                     |Avantages                                 |
|---------------------------|-------------------------|------------------------------------------|
|**WooCommerce** (WordPress)|Open source, auto-hébergé|Flexibilité, écosystème riche, coût modéré|
|**PrestaShop**             |Open source, auto-hébergé|Natif e-commerce, communauté FR forte     |
|**Shopify**                |SaaS                     |Simplicité, rapidité de déploiement       |
|**Medusa.js**              |Headless, open source    |Architecture moderne, API-first           |
|**Saleor**                 |Headless, open source    |GraphQL, scalable                         |

### 15.2 Hébergement

- Hébergeurs français recommandés : OVHcloud, Scaleway, Infomaniak (suisse, conforme RGPD)
- Localisation des données : privilégier un hébergement dans l’UE pour la conformité RGPD
- SSL/TLS inclus (Let’s Encrypt ou certificat commercial)

### 15.3 Services tiers essentiels

|Besoin                  |Solutions                                 |
|------------------------|------------------------------------------|
|CMP Cookies             |Axeptio, Tarteaucitron, Didomi            |
|Analytics               |Matomo (exemption CNIL), Plausible        |
|Email transactionnel    |Brevo (ex-Sendinblue), Mailjet            |
|Newsletter              |Brevo, Mailchimp (attention transferts US)|
|PSP Paiement            |Stripe, PayPlug, Mollie                   |
|Livraison / Expédition  |SendCloud, Boxtal, ShipStation            |
|Facturation électronique|Pennylane, Tiime, Abby, QuickBooks        |
|SAV / Helpdesk          |Crisp, Zendesk, Freshdesk                 |
|Avis clients            |Trustpilot, Avis Vérifiés, Judge.me       |

-----

## 16. CHECKLIST DE LANCEMENT

### Juridique & conformité

- [ ] Mentions légales rédigées et à jour
- [ ] CGV rédigées et accessibles, acceptation obligatoire avant commande
- [ ] Politique de confidentialité conforme RGPD
- [ ] Politique de cookies + CMP fonctionnelle (boutons Accepter/Refuser visibles)
- [ ] Déclaration d’accessibilité (si concerné par RGAA/EAA)
- [ ] Page médiation avec coordonnées du médiateur
- [ ] Formulaire de rétractation en ligne opérationnel (au plus tard le 19 juin 2026)
- [ ] Affichage prix antérieur sur les promotions (30 jours, Omnibus)
- [ ] Signalétique Triman + Info-tri sur les produits et emballages
- [ ] Indice de réparabilité/durabilité affiché (si catégories concernées)
- [ ] Adhésion REP en règle pour les filières concernées

### Technique

- [ ] HTTPS activé sur toutes les pages
- [ ] Performances Core Web Vitals conformes
- [ ] Sitemap XML soumis aux moteurs de recherche
- [ ] Robots.txt configuré
- [ ] Données structurées Schema.org sur les fiches produits
- [ ] Pages 404 et erreur personnalisées
- [ ] Responsive design (mobile-first)
- [ ] Tests cross-navigateurs (Chrome, Firefox, Safari, Edge)
- [ ] Sauvegardes automatiques configurées

### Paiement & logistique

- [ ] PSP intégré et testé (commande test complète)
- [ ] 3D Secure 2 activé
- [ ] Emails transactionnels configurés et testés (confirmation, expédition, etc.)
- [ ] Transporteurs intégrés avec calcul automatique des frais
- [ ] Factures conformes générées automatiquement
- [ ] Plateforme agréée de facturation électronique choisie et connectée (si B2B)

### Marketing & analytics

- [ ] Analytics installé et conforme RGPD
- [ ] Pixels marketing soumis au consentement cookies
- [ ] Emails de bienvenue et de panier abandonné configurés
- [ ] Comptes réseaux sociaux créés et liés
- [ ] Google Business Profile créé (si pertinent)

-----

## 17. SANCTIONS ENCOURUES — SYNTHÈSE

|Manquement                               |Sanction maximale                       |Base légale            |
|-----------------------------------------|----------------------------------------|-----------------------|
|Absence de mentions légales              |75 000 € + 1 an de prison               |LCEN art. 6-III-1      |
|Défaut d’information précontractuelle    |15 000 € (société)                      |Code conso. art. L131-1|
|Non-conformité RGPD                      |4 % du CA mondial ou 20 M€              |RGPD art. 83           |
|Non-conformité cookies/CMP               |4 % du CA mondial                       |RGPD + ePrivacy        |
|Absence de médiation                     |15 000 € (société)                      |Code conso. art. L641-1|
|Non-conformité accessibilité (ARCOM)     |50 000 € / service (renouvelable 6 mois)|RGAA                   |
|Non-conformité accessibilité (EAA/DGCCRF)|7 500 € + 3 000 €/jour (max 300 000 €)  |EAA transposée         |
|Absence déclaration accessibilité        |25 000 € (renouvelable 6 mois)          |RGAA                   |
|Facture non conforme (e-invoicing)       |15 €/facture (max 15 000 €/an)          |CGI                    |
|Données e-reporting manquantes           |250 €/donnée (max 15 000 €/an)          |CGI                    |
|Pratiques commerciales trompeuses        |300 000 € + 2 ans de prison             |Code conso. art. L132-2|
|Non-respect droit de rétractation        |Sanctions DGCCRF + prolongation du délai|Code conso.            |
|Greenwashing / allégations trompeuses    |300 000 € + 2 ans de prison             |Code conso.            |

-----

## SOURCES RÉGLEMENTAIRES DE RÉFÉRENCE

- **LCEN** — Loi n° 2004-575 du 21 juin 2004
- **Code de la consommation** — articles L111-1 et suivants, L221-18 et suivants
- **RGPD** — Règlement (UE) 2016/679
- **Ordonnance n° 2026-2** du 5 janvier 2026 (rétractation en ligne)
- **Directive EAA** — 2019/882 (accessibilité numérique)
- **RGAA 4.1.2** — Référentiel Général d’Amélioration de l’Accessibilité
- **Loi AGEC** — n° 2020-105 du 10 février 2020
- **DSA** — Règlement (UE) 2022/2065
- **Directive Omnibus** — 2019/2161 (transposée en droit français)
- **CGI** — art. 289 bis et suivants (facturation électronique)
- **Service-public.fr** — https://entreprendre.service-public.gouv.fr/vosdroits/F23455
- **CNIL** — Recommandations cookies et traceurs
- **economie.gouv.fr** — Facturation électronique

-----

> **⚠️ Avertissement** : Ce document constitue un guide structurel et informatif. Il ne remplace pas un conseil juridique professionnel. Les textes réglementaires évoluent ; vérifiez les dates d’entrée en vigueur au moment de votre lancement.

-----

*Dernière mise à jour : 23 avril 2026*