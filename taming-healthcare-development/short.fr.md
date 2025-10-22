---
marp: true
theme: gaia
paginate: false
style: |
  section {
    font-size: 36px;
    background-color: #efefe4ff;
    background-image: url('logo.svg');
    background-position: calc(100% - 20px) 100%;
    background-size: 80px 80px;
    background-repeat: no-repeat;
  }
  section h1 {
    font-size: 72px;
  }
  section h2 {
    font-size: 48px;
  }
  section li {
    font-size: 24px;
  }
  section li em {
    font-size: 36px;
  }
  section li b {
    font-size: 36px;
  }
  section.lead h1 {
    font-size: 72px;
  }
  section.lead h2 {
    font-size: 48px;
  }
---

<!-- _class: lead -->

![width:300px](logo.svg)

# Créer une Application Médicale
## Que pourrait-il mal se passer ?

*Dompter le développement en santé numérique*

**Antoine Duchâteau**

---

<!-- _class: lead -->

# La Liste du Startuper ✓

**Ce que vous pensez avoir besoin :**

- 📱 Une application mobile/web avec une belle interface
- 🔐 Un nom d'utilisateur et un mot de passe
- 💾 Une base de données pour stocker les données des patients
- ☁️ Un hébergement cloud (AWS, Azure, GCP)
- 🚀 Livrer vite, itérer plus vite

**Facile, non ?**

---

<!-- _class: lead -->

# Rebondissement

## Tout ce que vous avez négligé

*Bienvenue dans le développement en santé numérique*

---

# 🔑 Scénarios d'authentification

## Visez-vous le monde réel ?

---

# 🔑 Scénarios d'authentification

**Au-delà du nom d'utilisateur/mot de passe :**

- **Authentification multi-facteurs (MFA)** - Obligatoire pour les professionnels de santé
- **Connexion unique (SSO)** - Intégration avec les fournisseurs d'identité hospitaliers (SAML, OAuth)
- **Authentification par carte à puce** - Les professionnels médicaux utilisent souvent des cartes eID
- **Accès délégué** - Accès temporaire pour les collègues remplaçants, accès d'urgence

*Connexion simple ? Pas dans la santé.*

---

# 🛡️ Autorisations complexes

## Tout le monde peut tout voir, n'est-ce pas ?
---

# 🛡️ Autorisations complexes

**Pas seulement "connecté" vs "déconnecté" :**

- **Contrôle d'accès basé sur les rôles (RBAC)** - Médecins, infirmières, patients, admins
- **Contrôle d'accès basé sur les entités (EBAC)** - Contrôle d'accès granulaire aux données
- **Permissions hiérarchiques** - Niveaux département, institution, réseau de soins
- **Segmentation des données** - Santé mentale, statut VIH, diagnostics sensibles

*"L'utilisateur A peut-il accéder à la ressource B ?" devient incroyablement complexe.*

---

# 🔒 Confidentialité par chiffrement

## Les données de mes patients sont sûres, j'utilise HTTPS

---

# 🔒 Confidentialité par chiffrement

**Pas seulement HTTPS :**

- **Chiffrement de bout en bout** - Données chiffrées au repos ET en transit
- **Clés contrôlées par le patient** - Les patients possèdent leurs données cryptographiquement
- **Clés des professionnels médicaux** - Chaque prestataire a des clés de chiffrement uniques
- **Protocoles d'échange de clés** - Partage sécurisé entre parties autorisées
- **Architecture zero-knowledge** - Le serveur ne peut pas déchiffrer les données des patients

*La conformité RGPD nécessite des garanties cryptographiques, pas seulement des promesses.*

---

# 📚 Versionnement des données

## J'étais sûr d'avoir sauvegardé ça

---

# 📚 Versionnement des données

**Les dossiers médicaux ne sont pas que du CRUD :**

- **Piste d'audit immuable** - Jamais supprimer, seulement ajouter de nouvelles versions
- **Historique complet** - Chaque modification, qui l'a faite, quand et pourquoi
- **Comparaison de versions** - Diff entre versions à des fins légales/cliniques
- **Suppressions logiques** - Marquer comme supprimé mais conserver pour rétention légale
- **Mises à jour conflictuelles** - Plusieurs praticiens mettant à jour simultanément
- **Requêtes de voyage dans le temps** - "Que savions-nous de ce patient le 15 juin ?"

*Dans la santé, l'historique est aussi important que les données actuelles.*

---

# 📋 Traçabilité

## Faites-vous confiance à tout le monde ?

---

# 📋 Traçabilité

**Qui a fait quoi, quand et pourquoi :**

- **Journaux d'audit clinique** - Chaque accès et modification de données enregistré
- **Suivi des actions utilisateur** - Événements de lecture, écriture, suppression, export
- **Chaîne de traçabilité** - Provenance complète des données médicales
- **Non-répudiation** - Preuve cryptographique des actions entreprises
- **Journaux inviolables** - Les journaux eux-mêmes doivent être immuables et vérifiables
- **Preuve légale** - Les journaux d'audit doivent tenir devant un tribunal

*Si ce n'est pas enregistré, ça ne s'est pas produit (et vous êtes responsable).*

---

# 📊 Journalisation des accès

## Ce que nous ne voyons pas ne peut pas nous blesser 🫣

---

# 📊 Journalisation des accès

**Au-delà des analyses traditionnelles :**

- **Surveillance spécifique à la santé** - Qui a accédé à quels dossiers de patients ?
- **Alertes d'accès d'urgence** - L'accès d'urgence doit être enregistré et justifié
- **Détection de motifs suspects** - Modèles d'accès inhabituels, exports en masse
- **Rapports d'accès des patients** - Les patients peuvent voir qui a consulté leurs données (droit RGPD)
- **Rapports réglementaires** - Notification de violation, rapports d'accès pour les autorités
- **Alertes en temps réel** - Notification immédiate d'accès aux données sensibles
- **Rétention des journaux** - Conserver les journaux pendant 10-30 ans selon la juridiction

*Les violations de la vie privée peuvent vous fermer du jour au lendemain.*

---

# 🔍 Surveillance & sondage

## Tant que ça marche, ça marche

---

# 🔍 Surveillance & sondage

**Les SLA de santé sont vitaux :**

- **Exigences de disponibilité** - 99,99% ne suffit pas quand des vies en dépendent
- **Prévention des pannes** - La détection de défauts mineurs prévient les pannes majeures
- **Surveillance des performances** - Temps de réponse pour les fonctions cliniques critiques
- **Surveillance de la conformité** - Vérifications automatisées des exigences réglementaires
- **Sondage de sécurité** - Tests d'intrusion, analyse de vulnérabilités
- **Tests de reprise après sinistre** - Exercices réguliers, vérification des sauvegardes, tests de basculement

*L'arrêt dans la santé signifie un traitement retardé ou pire.*

---

# 🔗 Interopérabilité

## Mes données sont dans une base de données, de quoi d'autre aurais-je besoin ?

---

# 🔗 Interopérabilité

**Les systèmes de santé doivent communiquer entre eux :**

- **Formats standard** - HL7 FHIR, CDA, DICOM pour l'imagerie médicale
- **Systèmes de terminologie** - SNOMED CT, ICD-10, LOINC pour les résultats de laboratoire
- **Réseaux de santé nationaux** - Intégration avec les plateformes eSanté
- **Échange transfrontalier** - Résumé patient européen, IPS (International Patient Summary)
- **Intégrations de laboratoire** - Communication bidirectionnelle avec les systèmes de laboratoire
- **Systèmes d'information hospitaliers** - Flux ADT, planification de rendez-vous

*Votre application n'existe pas en isolation - elle fait partie d'un écosystème complexe.*

---

# ⚖️ Conformité réglementaire

## J'ai lu la nLPD une fois, ça va non ?

---

# ⚖️ Conformité réglementaire

**Bienvenue dans le labyrinthe réglementaire :**

- **RGPD** - Protection des données européennes (4% du chiffre d'affaires mondial d'amende)
- **Règlement sur les dispositifs médicaux (MDR)** - Votre app est-elle un dispositif médical ?
- **Certifications ISO** - ISO 13485 (dispositifs médicaux), ISO 27001 (sécurité)
- **Exigences de documentation** - Dossiers de gestion des risques, documentation technique
- **Surveillance post-commercialisation** - Surveillance continue et déclaration d'incidents

*La conformité réglementaire n'est pas une case à cocher - c'est un engagement continu.*

---

<!-- _class: lead -->

# La réalité

Créer une application médicale signifie :

🏗️ **Infrastructure** × 10 de complexité  
⚖️ **Conformité légale** × 100 d'effort  
🔐 **Sécurité** × 1000 de diligence  

*Mais vous protégez les données les plus sensibles qui existent : la santé des gens.*

---

<!-- _class: lead -->

# Questions ?

**La bonne nouvelle :** Des solutions existent. Cardinal gère la complexité, vous créez d'excellentes applications médicales.

*Concentrez-vous sur ce qui vous rend spécial.*

cardinalsdk.com - ad@icure.com