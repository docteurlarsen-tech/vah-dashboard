# VAH_Context_Claude.md
## Fichier de contexte maître — Village Artisanal Hybride
**Version :** 2.1
**Date :** 18 juin 2026
**Usage :** Uploader ce fichier au début de chaque nouvelle session Claude

---

## PROTOCOLE D'ACTIVATION

Quand Michael uploade ce fichier, Claude répond :
> *"Contexte VAH V2.1 chargé. Je suis au courant de tout. On reprend là où on s'était arrêtés. De quoi as-tu besoin ?"*

Claude demande ensuite les fichiers nécessaires selon le chantier du jour.

---

## 1. IDENTITÉ DU PROJET

**Fondateur & CPU :** Michael Ciré Bâ — 41 ans — Mbour, Sénégal
**Projet :** Village Artisanal Hybride (VAH) / La Fabrik'École
**Mission :** Fusionner artisanat traditionnel sénégalais et fabrication numérique
**Vision long terme :** Entreprise FDE africaine — le VAH est le terrain d'entraînement
**Boussole :** Dak'Art Biennale de Dakar 2028
**Deadline critique :** Fin février 2028 — dossier OFF soumis
**Engagement socle :** 2 ans · maintenant → Dak'Art 2028

**Trois composantes :**
- VAH — La matière · les réservoirs
- OV (Ordinateur Virtuel) — La mécanique · système de gouvernance · protégé copyright Michael
- Racines — Le sens · installation artistique itinérante · boussole Dak'Art 2028

**Les trois phases de la vision FDE :**
1. Monter l'équipe (maintenant → 2027) — VAH comme terrain de recrutement
2. Roder l'équipe (2027 → Dak'Art 2028) — Biennale comme premier grand déploiement
3. Déployer (post-2028) — Entreprise FDE africaine opérationnelle · financement · scale

---

## 2. RÈGLES DE TRAVAIL CLAUDE ↔ MICHAEL

- Toujours en français
- Partager la réflexion avant d'agir
- Valider architecture/structure avant exécution
- Construire par blocs progressifs
- Charles Haddad : vouvoiement systématique — TOUJOURS
- Style : direct, humain, jamais condescendant
- Pas de jargon OV spontané avec les acteurs
- Michael travaille 7j/7 — le travail est sa passion

---

## 3. LES ACTEURS

### PREMIER CERCLE — 4 FONDATEURS

**Michael Ciré Bâ — CPU / Fondateur**
- Colonne : Conception & Village numérique
- Commande CPU : /start START_MICHAEL
- Commande Acteur : /start START_MICHAEL_ACTEUR
- Statut : 🟢 Toujours opérationnel
- Apporte : Vision · architecture OV · CNC · systèmes numériques · formation

**Charles Haddad — Fabrication & Village physique**
- RÈGLE ABSOLUE : Vouvoiement systématique — jamais de "tu"
- Commande : /start START_CHARLES
- Apporte : Domaine Ngoltongo 50ha · atelier CNC · stock bois · Botanica 283 espèces
- Collection objets d'art non valorisée
- A mentionné préoccupation présence en ligne → clin d'œil bienveillant une seule fois

**Carole — Rayonnement & Portail (avec Michel · via Adwo Lodge)**
- Commande : /start START_CAROLE
- A proposé vitrine dépôt-vente · Michael a fait la menuiserie du lodge

**Michel — Rayonnement & Portail (avec Carole · via Adwo Lodge)**
- Commande : /start START_MICHEL
- Base Abidjan · réseau extérieur · pont ouest-africain
- Nom de famille à confirmer

### INVITÉS (3) — Exploration libre · pas de convergence
- /start START_INVITE_1
- /start START_INVITE_2
- /start START_INVITE_3
- Promotion possible : /cpu promouvoir [invite_id]

### NOTE : Babacar Cissé
Retiré des profils acteurs.
Reste dans Réservoir Compétences comme [RÉEL] — partenariat CNC existant Protosen Dakar.

### PREMIER CERCLE — Groupe B [SIM]
Benjamin Flahaut / Flao · Christian Thellier / Toons · Alexandre Ba · Abda N'Diaye

### QUARTET FONDATEUR
Michael + Alexandre + Benjamin + Christian

---

## 4. LES 3 COLONNES FONDATRICES

```
MICHAEL       → Conception & Village numérique
               vision · système · outils · coordination

CHARLES       → Fabrication & Village physique
               matière · territoire · moyens de production
               Sans lui : prototype uniquement

CAROLE+MICHEL → Rayonnement & Portail · via Adwo Lodge
               Carole intérieur · Michel extérieur Abidjan
               Sans eux : le système produit dans l'ombre
```

---

## 5. INFRASTRUCTURE TECHNIQUE — ÉTAT ACTUEL

### Agent Telegram V2.1
- Bot : Le Guide VAH
- Serveur : Railway · projet accurate-miracle
- Fichier : index.js V2.1 (882 lignes) — déployé 18/06/2026
- GitHub : docteurlarsen-tech/vah-agent (PRIVÉ)
- Modèle Claude : claude-sonnet-4-6 · max_tokens: 2048

**Commandes disponibles :**
- /start START_MICHAEL → Vue CPU (statuts · propositions · état système)
- /start START_MICHAEL_ACTEUR → Michael en mode participant
- /start START_CHARLES / CAROLE / MICHEL → Fondateurs
- /start START_INVITE_1/2/3 → Invités
- /profil → Voir son profil sauvegardé
- /reset → 4 types de reset
- /cpu recap → Rapport système complet
- /cpu promouvoir [invite_id] → Élever un invité

**Signaux dans les réponses Claude :**
- [SAUVEGARDER: apporte|valeur]
- [SAUVEGARDER: besoin|valeur]
- [SAUVEGARDER: role|valeur]
- [SAUVEGARDER: simulation|type-niveau]
- [PROP: réservoir|valeur|auteur]
- [SIGNAL_CPU: rouge|nom]
- [SIGNAL_CPU: convergence]

### Firebase
- URL : https://vah-simulation-default-rtdb.europe-west1.firebasedatabase.app
- Structure :
  /users/{chatId}/token · acteurId · historique
  /users/{chatId}/profil/ (apporte · besoin · role_choisi · statut · nb_sessions · nb_simulations · types_explores · derniere_session)
  /global/statuts/{acteurId} (statut · nom · type · date)
  /global/convergence
  /global/alertes
  /global/propositions (réservoir · valeur · acteur · date · statut)

### Dashboard CPU V2
- URL V2 : docteurlarsen-tech.github.io/vah-dashboard/dashboard-v2.html
- 4 onglets : Statuts · Réservoirs · Pool · Alertes
- Réservoirs modifiables depuis le dashboard
- À faire : onglet Propositions en attente

### Variables Railway
TELEGRAM_TOKEN · ANTHROPIC_KEY · FIREBASE_URL · GOOGLE_APPLICATION_CREDENTIALS_JSON

---

## 6. ARCHITECTURE DE SIMULATION V2.1

### 8 Types de simulation
A Artistique · B Technique · C Événementiel · D Économique
E Hybride · F Formation · G Institutionnel · H Patrimonial

### 4 Niveaux de réalité
[HYP] · [POT] · [RÉEL] · [ACTIF]

### 4 Modes d'entrée
1. Libre — choisir dans les 8 types
2. Adaptées — 3 propositions selon le profil
3. Graduée — Naturelle · Intermédiaire · Extravagante
4. Hasard — une combinaison aléatoire dans les 32

### Combinaison Claude — RÈGLE ABSOLUE
Toujours développée complètement · jamais une esquisse
Chemin en 3 temps : MAINTENANT · 2027 · DAK'ART 2028

### Structure de réponse
1. Reconnaissance · 2. Contenu · 3. Orientation (2-3) · 4. 1 question max
9 orientations disponibles · jamais terminer sans orientation

---

## 7. LES SIX PILIERS — PROJETS STRUCTURANTS

1. Fabrication à la Demande [RÉEL]
2. Collections — Signature · Hybride · Patrimoniale [RÉEL en construction]
3. Chantiers Participatifs — 3 missions [RÉEL à déployer]
4. Labo Itinérant / Remorque CNC [ACTIF en finalisation]
5. Sessions Expérimentales — R&D · matières récupérées [RÉEL à structurer]
6. Racines — installation itinérante · Dak'Art 2028 [RÉEL horizon 2028]

---

## 8. RÉSERVOIRS — ÉTAT ACTUEL

### Compétences
[RÉEL/ACTIF] : Michael CNC · Babacar Protosen (partenariat)
[POT] : domaines artisanaux · artisans numériques
[SIM] : Benjamin · Christian · Alexandre · Abda

### Matières
Bois Ngoltongo (Dimba · Caïcedrat · Vène · Azobé · Fraké · Ébène)
Matières récupérées [POT] · époxy · cuir · métal

### FabLabs
Sénégal [RÉEL/POT] · France [SIM]

### Statuts éléments réservoirs
Compétences : ⚪ NON CLASSÉ · 🔵 ÉVALUÉ · 🟡 AFFILIÉ · 🟢 ACTIF · 🔴 INACTIF · ⭐ PARRAIN
Projets : 💡 IDÉE · 📋 ÉTUDIÉ · ✅ VALIDÉ · 🔄 EN COURS · ✔️ LIVRÉ · ❌ SUSPENDU
Matières : ⚪ IDENTIFIÉ · 🔵 INVENTORIÉ · 🟡 RÉSERVÉ · 🟢 EN USE · 🔴 ÉPUISÉ · ⭐ SIGNATURE

---

## 9. SYSTÈME DE CONFIDENTIALITÉ & STATUTS

**Niveaux données :** 🔒 PRIVÉ · 👥 PARTAGÉ · 🎭 SIMULATION

**Statuts fondateurs :** ⚪ EN DÉCOUVERTE · 🟡 EN CONSTRUCTION · 🟢 OPÉRATIONNEL · 🔴 NE PARTICIPE PAS
**Statut invités :** 🎭 INVITÉ — exclus de la convergence

**Convergence :** 4 fondateurs actifs = 🟢 → signal CPU → réunion convoquée
(Les invités n'entrent PAS dans le calcul de convergence)

**Reset — 4 types :**
1. Conversation · 2. Simulation · 3. Données précises · 4. Complet (OUI requis)

---

## 10. POST-RÉUNION & FONDATIONS

**La réunion produit :** Accord de fondation · Table des apports · Charte PI · Feuille de route 90 jours
**Copyright :** Michael apporte système complet · proportionnalité selon apports
**Financement visé :** Charles et Michel en premier · co-investisseurs naturels
**Engagement :** 2 ans · sorties possibles
**Après 2028 :** Implantation · Village Physique Unifié · entreprise FDE africaine

---

## 11. CHANTIERS EN COURS

### ✓ Terminés
- index.js V2.1 déployé sur Railway
- Dashboard V2 en ligne (4 onglets)
- VAH_Synthese_V2.docx
- VAH_Document_FDE.docx (trame · à retravailler)
- Messages d'invitation Charles + groupe

### À faire
1. **Dashboard — onglet Propositions en attente**
   Afficher /global/propositions · valider/refuser depuis le dashboard

2. **VAH_Notice_Utilisation.docx**
   Guide utilisateur · 9 sections · ton humain · imprimable

3. **Document FDE — retours et corrections**
   Michael relit · retours · ajustement ton et formulations

4. **Tests V2.1 complets**
   8 types simulation · nouveaux profils · propositions · reset

---

## 12. FICHIERS À GARDER & QUAND LES UPLOADER

| Fichier | Rôle | Uploader quand |
|---------|------|----------------|
| VAH_Context_Claude.md | CE FICHIER | TOUJOURS en début de session |
| index.js | Serveur Telegram V2.1 | Modifier l'agent |
| dashboard-v2.html | Dashboard CPU | Modifier le dashboard |
| VAH_Document_FDE.docx | Document investisseurs | Retours et corrections |
| VAH_Synthese_V2.docx | Architecture complète | Référence |
| VAH_SystemPrompt_V1.docx | System prompt référence | Archivé |
| A01_V3_final.docx | Dossier de référence VAH | Mise à jour dossier |
| VAH_Message_Charles_Vouvoiement.docx | Message invitation Charles | Ajustement |
| VAH_Message_Groupe_Tutoiement.docx | Message invitation groupe | Ajustement |
| package.json | Config serveur | Changement librairies |

---

## 13. PROCHAINE SESSION

Uploader ce fichier + dire :
*"On reprend le VAH. Priorité aujourd'hui : [chantier choisi]"*

**Ordre recommandé :**
1. Dashboard — onglet Propositions
2. VAH_Notice_Utilisation.docx
3. Document FDE retours
4. Tests V2.1 complets
5. Accompagnement acteurs (quand tout est parfait)

---

*VAH · Village Artisanal Hybride · Michael Ciré Bâ · CPU · Mbour, Sénégal · 18 Juin 2026*
*Confidentiel — usage interne uniquement*
