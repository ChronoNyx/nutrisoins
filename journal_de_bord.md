# 📓 Journal de bord — Projet NUTRISOIN

---

# 📓 Journal de bord — Session 1

**Date de la session :** 10 mai 2026  
**Durée :** ~1 session de travail  
**Participants :** Vince (porteur du projet) + Claude (consultant stratégique)

---

## 🎯 Objectif de la session

Mettre en place les fondations techniques du site web **NUTRISOINS** :
- Création d'un dépôt de code
- Mise en ligne d'une première version du site
- Construction des sections principales du site

---

## ✅ Réalisations

### 1. Mise en place du dépôt GitHub
- ✅ Création du repo privé `ChronoNyx/nutrisoins`
- ✅ Configuration du remote Git local (`e:/nutrisoins`)
- ✅ Résolution des problèmes de configuration :
  - Mauvais remote (ancien compte `VinceD-code`) → corrigé vers `ChronoNyx`
  - Branche locale `master` → renommée en `main`
- ✅ Premier `pull` réussi puis premier `push` opérationnel

### 2. Mise en ligne via GitHub Pages
- ✅ Repo passé en **public** (prérequis GitHub Pages gratuit)
- ✅ Activation de GitHub Pages sur la branche `main`
- ✅ Site accessible publiquement à l'adresse :
  **`https://chrononyx.github.io/nutrisoins/`**

### 3. Construction du site `index.html`
Structure complète du site avec les sections suivantes :
- ✅ **Header** avec navigation et CTA "Prendre RDV"
- ✅ **Hero** avec photo de Michèle + texte rotatif animé
- ✅ **3 Pilliers** (Écoute / Expertise / Accompagnement durable)
- ✅ **Identification** ("Vous vous reconnaissez ?") — 6 situations parlantes
- ✅ **Ma Méthode** — 4 étapes du parcours client
- ✅ **Mes Offres** — 3 formules (Découverte / Programme / Ponctuelle)
- ✅ **À propos** de Michèle avec valeurs
- ✅ **Témoignages** (3 fictifs à remplacer)
- ✅ **Contact** avec formulaire et coordonnées
- ✅ **Footer** complet avec disclaimer santé

### 4. Identité visuelle
- ✅ Palette de couleurs verrouillée :
  - Vert olive `#3E4B31`
  - Ocre `#B56A3A`
  - Crème `#FDFBF8`
  - Beige `#F5F0E8`
- ✅ Typographies : **Playfair Display** (titres) + **Lato** (texte)
- ✅ Site **responsive** (desktop, tablette, mobile)

### 5. Gestion des assets
- ✅ Photo de Michèle (`Michele_Renault.JPG`) intégrée et compressée
- ✅ Logo SVG NUTRISOINS retravaillé (silhouette en lotus + chakra ocre, fidèle au bandeau email)

---

## ⚠️ Points de vigilance soulevés

### Propriété intellectuelle
- 🚫 **Logo Newtrition Coach retiré** du site → remplacé par une mention textuelle neutre ("réseau de formation reconnu")
- 📌 **À faire** : vérifier auprès du réseau Newtrition Coach si un kit communication "membre certifié" existe et quelles sont les règles d'usage du logo

### Conformité légale
- ✅ Disclaimer santé ajouté au footer ("Le coaching nutritionnel ne remplace pas une consultation médicale")
- 📌 **À faire** : rédiger les vraies **mentions légales** et la **politique de confidentialité**

### Contenu fictif
- ⚠️ Les **3 témoignages** sont fictifs → à remplacer dès que de vrais clients auront été accompagnés
- ⚠️ Les **tarifs** sont en "Sur demande" → à remplir une fois la grille tarifaire validée

---

## 🐛 Problèmes techniques rencontrés et résolus

| Problème | Solution appliquée |
|----------|-------------------|
| `remote origin already exists` avec mauvaise URL | `git remote remove origin` puis re-`add` |
| Branche locale `master` ≠ branche distante `main` | `git branch -m master main` |
| Repo privé incompatible avec GitHub Pages gratuit | Passage en public via Settings → Danger Zone |
| Photo de Michèle ne s'affichait pas (4 Mo) | Compression via Squoosh.app |
| Fichier renommé `Michele_Renault.JPG.JPG` (double extension) | `git rm` du mauvais fichier |
| Logo SVG initial non fidèle au bandeau email | Recréation du SVG : silhouette en lotus + point ocre central |

---

## 📋 État actuel du projet (fin session 1)

### Ce qui est en ligne
- 🟢 Site vitrine fonctionnel à `https://chrononyx.github.io/nutrisoins/`
- 🟢 Repo de code synchronisé entre local et GitHub
- 🟢 Workflow Git en place (push pour publier les modifications)

### Architecture technique
```
e:/nutrisoins/
├── index.html              ← Site complet (~50 Ko)
├── Michele_Renault.JPG     ← Photo profil compressée
├── README.md               ← Description du repo
└── .git/                   ← Suivi de version
```

---

## 🚀 Prochaines étapes suggérées (à l'issue de la session 1)

### Court terme
1. **Mentions légales & RGPD**
2. **Formulaire de contact fonctionnel** (Formspree, EmailJS)
3. **Domaine personnalisé** `nutrisoins.be`

### Moyen terme
4. **SEO de base** (Google Business Profile, Search Console, sitemap)
5. **Vérifications réseau** Newtrition Coach
6. **Réseaux sociaux** (Instagram, Facebook)
7. **Témoignages réels**

### Long terme
8. **Stratégie de contenu / Blog**
9. **Tarifs et offres définitives**
10. **Préparation de l'activité nutrithérapie**

---

## 💡 Notes & observations (session 1)

- L'approche **GitHub Pages + HTML statique** est parfaitement adaptée pour démarrer : 0 € d'hébergement, déploiement automatique à chaque `git push`.
- La **vraie photo professionnelle** de Michèle apporte beaucoup de chaleur au site.
- Le **logo en lotus** avec le point ocre central renforce l'identité bien-être/nutrition holistique.

---

*Fin de session 1 — Bonne continuation ! 🌿*

---

# 📓 Journal de bord — Session 2

**Date de la session :** 11 mai 2026  
**Durée :** ~1 session de travail  
**Participants :** Vince (porteur du projet) + Claude (consultant stratégique)

---

## 🎯 Objectif de la session

Protéger les données personnelles de Michèle avant la mise en production du site.

---

## ✅ Réalisations

### 1. Audit de confidentialité
- ✅ Identification de toutes les données personnelles indexables dans `index.html` :
  - Nom complet "Michèle Renault"
  - Adresse complète (Rue des Bruyères 256, 5310 Waret-la-Chaussée)
  - Numéro de téléphone personnel/pro (+32 475/82.60.35)
  - Numéro BCE (0812.541.218)
- ✅ Vérification : site non indexé par Google et non archivé par Wayback Machine pendant ses 10h en ligne

### 2. Décisions de confidentialité prises

| Donnée | Décision | Justification |
|--------|----------|--------------|
| Nom complet "Michèle Renault" | Réduit à "Michèle" partout | Domicile privé = protection vie privée |
| Adresse précise | → "Waret-la-Chaussée (à 15 min de Namur)" | Adresse = domicile privé |
| Téléphone | Supprimé totalement | GSM perso/pro, risque spam |
| BCE | Supprimé (temporaire) | Site hors prod, à remettre avant lancement |

### 3. Modifications appliquées dans `index.html`
- ✅ `<title>` : nom retiré
- ✅ `<meta description>` : "Michèle Renault" → "Michèle"
- ✅ Hero et À propos : `alt` images nettoyés
- ✅ Section À propos : "Waret-la-Chaussée" retiré du texte
- ✅ Section Contact : restructurée (adresse partielle + formulaire comme canal unique, téléphone supprimé)
- ✅ Footer : texte brand mis à jour, BCE retiré temporairement

### 4. Renommage de la photo
- ✅ `Michele_Renault.JPG` → `coach-nutrition-namur.jpg`
- ✅ `git mv` exécuté + références HTML mises à jour
- ✅ Bonus SEO : nom de fichier neutre et descriptif

### 5. Résolution de bugs Git
- ✅ `git push --set-upstream origin main` : branche locale configurée pour suivre `origin/main` (désormais `git push` suffit)
- ✅ Correction casse fichier image : `.JPG` → `.jpg` (Linux/GitHub Pages sensible à la casse)

---

## ⚠️ Points de vigilance soulevés

### À remettre avant la mise en production
- 📌 **BCE** : obligatoire dans les mentions légales et/ou footer une fois l'activité active (AR du 22 février 2006 + Code de droit économique Livre III)
- 📌 **Numéro de contact** : envisager un numéro pro dédié (~10€/mois) pour pouvoir l'afficher publiquement
- 📌 **Mentions légales** complètes (BCE, hébergeur, responsable)
- 📌 **Politique de confidentialité RGPD** (le formulaire collecte des données personnelles)

### SEO local — compensation de l'adresse retirée
- 📌 Configurer le **Google Business Profile** en mode "zone de service" (sans adresse publique affichée) — permet de garder la visibilité locale sans exposer le domicile

---

## 🐛 Problèmes techniques rencontrés et résolus

| Problème | Solution appliquée |
|----------|-------------------|
| `fatal: The current branch main has no upstream branch` | `git push --set-upstream origin main` |
| Photo disparue après renommage | Casse `.JPG` ≠ `.jpg` sur Linux — corrigé dans le HTML |
| Résidus de données perso dans l'ancien `index.html` local | Édition directe via connecteur Filesystem |
| Connecteur GitHub non disponible en session | Diagnostic via Filesystem + lecture directe du fichier local |

---

## 📋 État actuel du projet (fin session 2)

### Fichiers dans le repo
```
e:/nutrisoins/
├── index.html                  ← Site nettoyé (données perso protégées)
├── coach-nutrition-namur.jpg   ← Photo (renommée, neutre et SEO-friendly)
├── Image_newtricoach.svg       ← Logo réseau (SVG)
├── journal_de_bord.md          ← Ce fichier
└── README.md                   ← Mis à jour
```

### Données personnelles dans le HTML
- 🟢 Nom complet : retiré
- 🟢 Adresse précise : retirée
- 🟢 Téléphone : retiré
- 🟢 BCE : retiré (temporaire)
- 🟡 Nom de fichier image : neutre (`coach-nutrition-namur.jpg`)

---

## 🚀 Prochaines étapes (session 3)

1. **Formulaire de contact fonctionnel** — connecter à Formspree ou EmailJS
2. **Mentions légales + politique de confidentialité RGPD**
3. **Google Business Profile** en mode zone de service
4. **Domaine nutrisoins.be** — vérifier disponibilité et configurer DNS

---

*Fin de session 2 — Bonne continuation ! 🌿*

---

# 📓 Journal de bord — Session 3

**Date de la session :** 11 mai 2026  
**Durée :** ~1 session de travail  
**Participants :** Vince (porteur du projet) + Claude (consultant stratégique)

---

## 🎯 Objectif de la session

Amélioration de l'expérience utilisateur du hero et nettoyage éditorial du site.

---

## ✅ Réalisations

### 1. Hero — sous-titres rotatifs synchronisés
- ✅ Ajout d'un bloc `.hero-sub-wrap` avec 5 sous-titres (`.hero-sub-slot`) animés
- ✅ Synchronisation avec le mot rotatif existant : chaque mot correspond à un sous-titre distinct
- ✅ Animation CSS : entrée par glissement + fondu (`translateY` + `opacity`), délai `0.1s` pour décalage naturel
- ✅ Intervalle de rotation : 4 secondes (ajustable via `setInterval`)
- ✅ Les 5 combinaisons mot / sous-titre :
  | Mot | Sous-titre |
  |-----|-----------|
  | Naturellement. | Alimentation juste, durable et sans culpabilité |
  | Durablement. | Approche bienveillante et personnalisée |
  | À votre rythme. | Adaptation à votre corps, votre vie |
  | Sans privation. | Relation apaisée et durable avec la nourriture |
  | Avec bienveillance. | Manger bien sans frustration ni comptage |

### 2. Section Offres — corrections éditoriales
- ✅ Badge carte "Programme Suivi" : `⭐ Le plus choisi` → `⭐ Conseillé`
- ✅ Durée programme : `/ 3 mois` → `/ 12 semaines` (badge + description)

### 3. Section Témoignages — suppression
- ✅ Section `<section class="temoignages">` entièrement retirée (HTML + styles CSS associés)
- ✅ Justification : témoignages fictifs, section à recréer uniquement avec de vrais retours clients

### 4. Section À propos — logo dans le titre
- ✅ Emoji 👋 remplacé par le logo SVG `logo_nutrisoins.svg` inline dans le `<h2>`
- ✅ Dimensions : `width: 48px; height: 48px; vertical-align: middle; margin-left: 8px`

---

## 💡 Notes techniques (session 3)

- **Réglage des transitions CSS** : `opacity Xs ease Ys` = propriété / durée / courbe / délai. Le délai `0.1s` sur le sous-titre crée un léger décalage visuel par rapport au mot rotatif — effet naturel.
- **Courbes disponibles** : `ease` (défaut, asymétrique), `ease-out` (recommandé contenu éditorial), `linear`, `ease-in`, `ease-in-out`.
- **Tip fondu long** : pour un fondu perceptible signalant le prochain changement, monter la transition à `1.2s` et l'intervalle à `5000ms` — temps de lecture nette ≈ 3.8s, fondu visible ≈ 1.2s.
- **PowerShell** : `&&` non supporté — utiliser les commandes Git séparées ligne par ligne.

---

## 🐛 Problèmes techniques rencontrés et résolus

| Problème | Solution appliquée |
|----------|-------------------|
| `&&` non valide en PowerShell pour chaîner les commandes Git | Commandes `git add`, `git commit`, `git push` lancées séparément |
| Connecteur `filesystem:edit_file` refusé sur `E:\nutrisoins` | Fichier reconstruit dans l'env. Claude puis téléchargé et remplacé manuellement |

---

## 📋 État actuel du projet (fin session 3)

### Fichiers dans le repo
```
e:/nutrisoins/
├── index.html                  ← Site mis à jour (hero rotatif complet, témoignages supprimés)
├── coach-nutrition-namur.jpg   ← Photo profil
├── logo_nutrisoins.svg         ← Logo (utilisé dans header + section À propos)
├── Image_newtricoach.jpeg      ← Logo réseau Newtrition Coach
├── journal_de_bord.md          ← Ce fichier
└── README.md
```

### État des sections du site
- 🟢 Hero : mot rotatif + sous-titre synchronisé (5 combinaisons)
- 🟢 Pilliers : OK
- 🟢 Identification : OK
- 🟢 Ma Méthode : OK
- 🟢 Mes Offres : badge et durée corrigés
- 🟢 À propos : logo SVG dans le titre
- 🔴 Témoignages : supprimée (à recréer avec vrais retours clients)
- 🟡 Contact : formulaire non connecté (Formspree/EmailJS à faire)
- 🟢 Footer : OK

---

## 🚀 Prochaines étapes (session 4)

1. **Formulaire de contact fonctionnel** — connecter à Formspree ou EmailJS
2. **Mentions légales + politique de confidentialité RGPD**
3. **Google Business Profile** en mode zone de service
4. **Domaine nutrisoins.be** — vérifier disponibilité et configurer DNS

---

*Fin de session 3 — Bonne continuation ! 🌿*

---

# 📓 Journal de bord — Session 4

**Date de la session :** 11 mai 2026  
**Durée :** ~1 session de travail  
**Participants :** Vince (porteur du projet) + Claude (consultant stratégique)

---

## 🎯 Objectif de la session

Mise en place d'un système de prise de rendez-vous en ligne via **Cal.com** et intégration dans le site.

---

## ✅ Réalisations

### 1. Choix et création du compte Cal.com
- ✅ Outil retenu : **Cal.com** (gratuit, RGPD-friendly, hébergement EU possible)
- ✅ Compte créé avec l'identifiant : `vincent-qxx86o` (compte test de Vince — à remplacer par le compte de Michèle avant le lancement)
- ✅ URL de base : `cal.com/vincent-qxx86o`

### 2. Création des 4 types de rendez-vous

| Event type | URL slug | Durée | Mode |
|-----------|----------|-------|------|
| Séance Découverte — Coaching Nutrition | `decouverte` | 45 min | Présentiel ou en ligne |
| Bilan Initial — Programme Suivi 12 semaines | `bilan-initial` | 75 min | Présentiel uniquement |
| Séance Ponctuelle — Conseil Nutritionnel | `seance-ponctuelle` | 60 min | Présentiel ou en ligne |
| Séance de Suivi — Programme 12 semaines | `suivi-programme` | 60 min | En ligne uniquement |

### 3. Questions de réservation configurées

**Séance Découverte & Séance Ponctuelle :**
1. Quel est votre objectif principal ? *(obligatoire)*
2. Avez-vous déjà suivi un coaching ou un régime ? *(Oui/Non, obligatoire)*
3. Préférence : présentiel ou en ligne ? *(obligatoire)*
4. Y a-t-il quelque chose d'important que Michèle devrait savoir ? *(optionnel)*

**Bilan Initial — Programme 12 semaines :**
1. Quels sont vos objectifs pour ce programme ? *(obligatoire)*
2. Avez-vous déjà suivi un coaching ou un régime ? *(Oui/Non, obligatoire)*
3. Y a-t-il quelque chose d'important que Michèle devrait savoir ? *(optionnel)*
*(pas de question présentiel/ligne — d'office en présentiel)*

**Séance de Suivi :**
1. Depuis notre dernière séance, qu'est-ce qui a bien fonctionné ? *(obligatoire)*
2. Quelles difficultés avez-vous rencontrées ? *(obligatoire)*
3. Y a-t-il quelque chose de particulier à aborder ? *(optionnel)*

### 4. Disponibilités configurées

| Jour | Plage(s) |
|------|----------|
| Lundi | 17h00 → 20h00 |
| Mardi | 17h00 → 20h00 |
| Mercredi | 16h00 → 20h00 |
| Jeudi | 17h00 → 20h00 |
| Vendredi | 16h00 → 19h00 |
| Samedi | 10h00 → 12h00 et 14h00 → 18h00 |
| Dimanche | Fermé |

- ✅ Timezone réglée sur **Europe/Brussels**
- ✅ **Slot interval** réglé à **60 min** sur tous les event types (créneaux proposés toutes les heures, indépendamment de la durée de la séance)

### 5. Personnalisation du profil Cal.com
- ✅ Nom affiché : `Michèle — NUTRISOINS`
- ✅ Logo yogi/lotus NUTRISOINS uploadé
- ✅ Bio courte ajoutée

### 6. Intégration dans `index.html`
- ✅ Bouton **"PRENDRE RDV"** du header → `cal.com/vincent-qxx86o`
- ✅ CTA Séance Découverte → `cal.com/vincent-qxx86o/decouverte`
- ✅ CTA Programme Suivi → `cal.com/vincent-qxx86o/bilan-initial`
- ✅ CTA Séance Ponctuelle → `cal.com/vincent-qxx86o/seance-ponctuelle`
- ✅ Tous les liens s'ouvrent en `target="_blank"`
- ✅ `git push` effectué — modifications en ligne

---

## ⚠️ Points de vigilance soulevés

- 📌 **Compte de test** : l'identifiant `vincent-qxx86o` est provisoire. Avant le lancement officiel, créer le compte Cal.com définitif avec l'email de Michèle (idéalement `michele@nutrisoins.be`) et remplacer toutes les occurrences dans `index.html` (simple chercher/remplacer).
- 📌 **Adresse présentiel** : configurer l'adresse dans Cal.com une fois décidée (domicile ou local dédié).
- 📌 **Connexion agenda Google** : connecter le Google Agenda de Michèle pour synchronisation automatique des disponibilités.

---

## 🐛 Problèmes techniques rencontrés et résolus

| Problème | Solution appliquée |
|----------|-------------------|
| Connecteur Filesystem refusait l'accès à `E:\nutrisoins` | Répertoire ajouté dans les allowed directories — accès opérationnel en fin de session |
| Cal.com propose des créneaux par blocs égaux à la durée (ex. 16h/17h30 pour 90 min) | Réglage du **Slot interval** à 60 min dans chaque event type |
| "Attendee's choice" non disponible en version gratuite | Remplacé par une question de réservation "Présentiel ou en ligne ?" |

---

## 📋 État actuel du projet (fin session 4)

### Fichiers dans le repo
```
e:/nutrisoins/
├── index.html                  ← Liens Cal.com intégrés sur tous les CTA
├── coach-nutrition-namur.jpg   ← Photo profil
├── logo_nutrisoins.svg         ← Logo
├── Image_newtricoach.jpeg      ← Logo réseau
├── journal_de_bord.md          ← Ce fichier (mis à jour)
└── README.md
```

### État des sections du site
- 🟢 Hero : mot rotatif + sous-titre synchronisé
- 🟢 Offres : 3 CTA connectés à Cal.com
- 🟢 Header : bouton "PRENDRE RDV" connecté à Cal.com
- 🔴 Témoignages : supprimée (vrais retours clients à venir)
- 🟡 Contact : formulaire non connecté (Formspree/EmailJS à faire)
- 🟡 Cal.com : compte test — à basculer sur le compte définitif de Michèle

---

## 🚀 Prochaines étapes (session 5)

1. **Formulaire de contact** — connecter à Formspree ou EmailJS
2. **Mentions légales + politique de confidentialité RGPD**
3. **Google Business Profile** en mode zone de service
4. **Domaine nutrisoins.be** — vérifier disponibilité et configurer DNS
5. **Basculer Cal.com** sur le compte définitif de Michèle

---

*Fin de session 4 — Bonne continuation ! 🌿*

---

# 📓 Journal de bord — Session 5

**Date de la session :** 12 mai 2026  
**Durée :** ~1 session de travail  
**Participants :** Vince (porteur du projet) + Claude (consultant stratégique)

---

## 🎯 Objectif de la session

Migration de l'hébergement de GitHub Pages vers **Vercel** et configuration du domaine personnalisé `nutrisoins.be`.

---

## ✅ Réalisations

### 1. Décision d'hébergement — GitHub Pages → Vercel
- ✅ Comparatif GitHub Pages vs Vercel réalisé
- ✅ Vercel retenu pour ses avantages : CDN edge performant, analytics intégrés, fonctions serverless (formulaire de contact futur), previews de déploiement
- ✅ Stratégie retenue : configurer le domaine maintenant, brancher le repo quand Michèle donne le feu vert

### 2. Configuration du domaine `nutrisoins.be` dans Vercel
- ✅ Domaine ajouté au projet placeholder `project-coach` dans Vercel
- ✅ Records DNS configurés dans la zone OVH :
  - `@` / A / `216.198.79.1` (nouveau record Vercel — IP range expansion)
  - `www` / CNAME / `cname.vercel-dns.com.` (après suppression des anciens records OVH)
- ✅ Propagation DNS immédiate (< 30 min)
- ✅ Statut Vercel : **Valid Configuration** ✅

### 3. Clarification — mention du webmaster
- ✅ Décision : le webmaster (Vince) **ne figure pas** sur le site public
- ✅ Seul le responsable de publication (Michèle) apparaîtra dans les mentions légales
- ✅ La paternité technique reste dans l'historique Git (README)

---

## ⚠️ Points de vigilance soulevés

- ⚠️ **Action Required Vercel** : adresse de facturation manquante sur le compte — à compléter (même en Hobby/gratuit)
- 📌 **Records email OVH préservés** : MX, SPF, DKIM (`ovhmo-selector`) non touchés — nécessaires pour la future adresse `@nutrisoins.be`

---

## 🐛 Problèmes techniques rencontrés et résolus

| Problème | Solution appliquée |
|----------|-------------------|
| Vercel n'affichait pas les records DNS dans la vue domaines du projet | Navigation via Settings → Domains du projet → "Learn more" pour afficher les records |
| Record `www` OVH existant (A `213.186.33.5` + TXT `"3|welcome"`) bloquait l'ajout du CNAME | Suppression des deux records OVH avant ajout du CNAME Vercel |
| Interface Vercel confuse entre gestion globale et gestion par projet | Records DNS trouvés dans Settings → Domains du projet `project-coach` |

---

## 📋 État actuel du projet (fin session 5)

### Infrastructure
- 🟢 `nutrisoins.be` → pointé vers Vercel (Valid Configuration)
- 🟡 Repo `ChronoNyx/nutrisoins` → encore sur GitHub Pages (à basculer sur Vercel au feu vert de Michèle)
- 🟡 GitHub Pages → encore actif (à désactiver lors du branchement)

### Fichiers dans le repo
```
e:/nutrisoins/
├── index.html                  ← Inchangé cette session
├── coach-nutrition-namur.jpg   ← Photo profil
├── logo_nutrisoins.svg         ← Logo
├── Image_newtricoach.jpeg      ← Logo réseau
├── journal_de_bord.md          ← Ce fichier (mis à jour)
└── README.md
```

---

## 🚀 Prochaines étapes (session 6)

1. **Brancher le repo sur Vercel** — quand Michèle valide le site
2. **Désactiver GitHub Pages** — lors du branchement
3. **Compléter l'adresse de facturation** sur le compte Vercel
4. **Formulaire de contact** — connecter à Formspree ou fonction Vercel serverless
5. **Mentions légales + politique de confidentialité RGPD**
6. **Google Business Profile** en mode zone de service
7. **Basculer Cal.com** sur le compte définitif de Michèle (`michele@nutrisoins.be`)

---

*Fin de session 5 — Bonne continuation ! 🌿*

---

# 📓 Journal de bord — Session 6

**Date de la session :** 12 mai 2026  
**Durée :** ~1 session longue  
**Participants :** Vince (porteur du projet) + Claude (consultant stratégique)

---

## 🎯 Objectif de la session

Finaliser deux des chantiers en attente :
1. Formulaire de contact fonctionnel
2. Mentions légales + politique de confidentialité RGPD

Plus quelques améliorations UX et esthétiques.

---

## ✅ Réalisations

### 1. Formulaire de contact — connexion Formspree
- ✅ Compte Formspree créé — endpoint `https://formspree.io/f/xrejjlqz`
- ✅ Destination des messages : `renault.demptinne@gmail.com` (modifiable depuis le dashboard Formspree sans toucher au code)
- ✅ Transformation du faux `<div>` en vrai `<form>` HTML avec attributs `name` corrects
- ✅ Soumission **Ajax via `fetch`** (pas de rechargement de page)
- ✅ Gestion complète des états :
  - Pendant l'envoi : bouton grisé + "Envoi en cours…" → empêche double-clic
  - Succès : formulaire masqué, encart de confirmation affiché avec le **logo lotus NUTRISOINS** (au lieu de l'emoji ✅ générique)
  - Erreur : message contextuel + bouton réactivé
- ✅ Champ honeypot `_gotcha` anti-spam (invisible aux humains)
- ✅ Validation HTML native (`required` sur tous les champs essentiels)
- ✅ Abandon de la lib `@formspree/ajax` CDN au profit d'un `fetch` direct (plus léger, plus fiable, sans dépendance externe)

### 2. Mentions légales (`mentions-legales.html`)
Nouvelle page créée avec :
- Éditeur : Michèle Renault-Demptinne, indépendante à titre complémentaire
- BCE marqué "en cours d'attribution" avec note explicative (à mettre à jour dès réception)
- Hébergeur : Vercel Inc. (anticipation de la migration future)
- Propriété intellectuelle (avec mention de l'autorisation d'usage du logo Newtrition Coach)
- Disclaimer médical encadré
- Liens tiers, droit applicable belge, juridiction Namur
- Charte graphique calée sur celle du site (mêmes variables CSS, mêmes polices)

### 3. Politique de confidentialité RGPD (`politique-confidentialite.html`)
Nouvelle page créée avec :
- Responsable de traitement clairement identifié
- Données collectées (uniquement via formulaire — pas de tracking)
- Tableau finalités / bases légales (art. 6.1.b et 6.1.f RGPD)
- Destinataires : Formspree (sous-traitant) + Cal.com
- Durées de conservation (3 ans messages / 5 ans comptable)
- Section spécifique Cal.com
- Mention claire "aucun cookie de tracking"
- Les 6 droits RGPD détaillés
- Coordonnées APD belge pour les réclamations

### 4. Connexion des liens du footer
- ✅ "Mentions légales" → `mentions-legales.html`
- ✅ "Politique de confidentialité" → `politique-confidentialite.html`
- ✅ "Newtrition Coach" → `https://newtritioncoach.org/` (était un lien mort `#`)
- ✅ Logo Facebook → `https://www.facebook.com/profile.php?id=61589545773180`

### 5. Logo Newtrition Coach — affichage dans la section Méthode
- ✅ Michèle a obtenu l'autorisation d'utiliser le logo Newtrition Coach
- ✅ Référence corrigée dans `index.html` : `Image_newtricoach.jpeg` (inexistant) → `Image_newtricoach.svg` (existant)
- ✅ Logo rendu cliquable → lien vers `https://newtritioncoach.org/` avec `rel="noopener noreferrer"`

### 6. Favicon
- ✅ Ajout du logo lotus NUTRISOINS comme favicon (`<link rel="icon" type="image/svg+xml" href="logo_nutrisoins.svg">`)
- ✅ Appliqué sur les 3 pages (index + 2 pages légales)

---

## ⚠️ Points de vigilance soulevés

### Mentions légales — à mettre à jour
- 📌 **Numéro BCE** : dès réception, remplacer la mention "en cours d'attribution" dans `mentions-legales.html`
- 📌 Si l'hébergeur change finalement (rester sur GitHub Pages plutôt que migrer vers Vercel), ajuster la section hébergeur

### Cohérence visuelle — chantier futur
- 📌 Le chat IA d'onboarding (`C:\nutrisoins_ia`) utilise une palette verte (`#2D8B6F`) différente du site vitrine (`#3E4B31`). À harmoniser **plus tard**, dans le cadre d'une refonte plus large du chat (revue du prompt système + création d'une page admin pour Michèle).

### Esthétique — à venir
- 📌 Remplacement des **emojis** (🌿 🎓 🤝 📍 ✉️ 💻 ⭐ 🌱 🌾…) par des **icônes SVG** sur-mesure dans la teinte ocre (`#B56A3A`)
- Décision : génération des icônes via Gemini avec un brief précis (style line-icons minimalistes, stroke fin, cohérent avec le logo lotus)
- Brief de génération sauvegardé dans le condensé du journal

---

## 🐛 Problèmes techniques rencontrés et résolus

| Problème | Solution appliquée |
|----------|-------------------|
| Lib `@formspree/ajax` ne déclenchait pas l'affichage de la confirmation `data-fs-success` | Abandon de la lib, réécriture en `fetch` natif avec gestion manuelle des états DOM |
| Risque que l'utilisateur renvoie plusieurs messages | Verrouillage `disabled` du bouton pendant l'envoi + masquage complet du formulaire en cas de succès |
| Image Newtrition Coach cassée (icone d'image brisée dans le HTML) | Référence `.jpeg` corrigée en `.svg` |
| Liens morts dans le footer (`href="#"`) | Tous remplacés par les vraies URLs (pages internes + réseau + Facebook) |

---

## 📋 État actuel du projet (fin session 6)

### Fichiers dans le repo
```
C:/nutrisoins/
├── index.html                       ← Formulaire fonctionnel, footer câblé, favicon
├── mentions-legales.html            ← NOUVEAU
├── politique-confidentialite.html   ← NOUVEAU
├── coach-nutrition-namur.jpg        ← Photo profil
├── logo_nutrisoins.svg              ← Logo (header, à propos, accusé envoi, favicon)
├── Image_newtricoach.svg            ← Logo réseau (autorisé, cliquable)
├── journal_de_bord.md               ← Archive complète (ce fichier)
└── README.md
```

### État des sections du site
- 🟢 Hero : OK
- 🟢 Pilliers : OK
- 🟢 Identification : OK
- 🟢 Méthode : OK (logo Newtrition cliquable)
- 🟢 Offres : OK (3 CTA Cal.com)
- 🟢 À propos : OK
- 🟢 Contact : **formulaire FONCTIONNEL** ✅
- 🟢 Footer : OK (tous liens câblés)
- 🟢 Mentions légales : OK (BCE à actualiser)
- 🟢 Politique RGPD : OK

### Chantiers du début de session 6 — statut
- 🟢 1. Formulaire contact fonctionnel — **TERMINÉ**
- 🟢 2. Mentions légales + RGPD — **TERMINÉ**
- 🟡 3. Google Business Profile zone de service — à faire
- 🟡 4. Branchement repo sur Vercel + désactivation GitHub Pages — à faire
- 🟡 5. Bascule Cal.com sur compte définitif Michèle — à faire

---

## 🚀 Prochaines étapes (session 7)

1. **Icônes SVG sur-mesure** — génération via Gemini + intégration
2. **Branchement repo sur Vercel** + désactivation GitHub Pages (le DNS `nutrisoins.be` est déjà prêt depuis la session 5)
3. **Google Business Profile** en mode zone de service
4. **Bascule Cal.com** sur le compte définitif de Michèle

### Chantier futur (hors session courte)
- **Refonte du chat IA d'onboarding** (`C:\nutrisoins_ia`) :
  - Revue du prompt système de l'IA
  - Harmonisation graphique avec la charte du site
  - Création d'une page admin pour Michèle (consultation des résumés, gestion des liens token)
  - Workflow d'envoi automatique du lien d'onboarding après réservation Cal.com

---

## 💡 Notes & observations (session 6)

- **Pattern journal long + condensé** mis en place à partir de cette session :
  - `journal_de_bord.md` reste l'archive détaillée dans le repo
  - `journal_condense.md` (dans les fichiers du projet Claude) sert de mémoire de travail pour les prochaines sessions
- **Le `fetch` natif est souvent plus fiable que les libs JS tierces** pour des cas simples comme un formulaire. La lib `@formspree/ajax` ajoutait de la complexité et une dépendance réseau sans valeur ajoutée pour notre cas.
- **Le favicon SVG** est supporté par tous les navigateurs modernes — plus besoin d'exporter en `.ico` ou de générer plusieurs résolutions PNG. Bonus : il reste net à toute taille.

---

*Fin de session 6 — Bonne continuation ! 🌿*

---

# 📓 Journal de bord — Session 7

**Date de la session :** 12 mai 2026  
**Durée :** ~1 session courte  
**Participants :** Vince (porteur du projet) + Claude (consultant stratégique)

---

## 🎯 Objectif de la session

Appliquer les corrections demandées par Michèle après sa première revue complète du site.

---

## ✅ Réalisations

### Corrections `index.html`

| # | Zone | Modification |
|---|------|--------------|
| 1 | Hero — JS | Vitesse de rotation : `7000ms` → **`9000ms`** |
| 2 | Offres — carte gauche | **Séance Découverte** supprimée, remplacée par **Séance Ponctuelle** (repositionnée) |
| 3 | Offres — carte droite | Ancienne Séance Ponctuelle remplacée par **Suivi Programme** (séances de suivi du programme 12 semaines) |
| 4 | Méthode — étape 2 | Texte "Construction d'un programme nutritionnel adapté à vous, pas à un archétype théorique." → nouveau texte sur-mesure de Michèle |
| 5 | À propos — titre | "Bonjour, je suis Michèle" → **"Je m'appelle Michèle"** |
| 6 | À propos — 1er §  | Reformulation : "Coach en nutrition certifiée basée près de Namur, j'accompagne…" → "Je suis coach en nutrition certifiée, basée près de Namur. J'accompagne…" |
| 7 | Contact — cabinet | "Waret-la-Chaussée" → **"Eghezée"** |

### Correction `mentions-legales.html`

| # | Zone | Modification |
|---|------|--------------|
| 8 | Éditeur — zone d'activité | "Waret-la-Chaussée et région namuroise (Belgique)" → **"Eghezée et région namuroise"** |

### Réorganisation des offres — logique retenue
Nouvelle grille (gauche → centre → droite) :
1. **Séance Ponctuelle** — conseil ciblé, présentiel ou en ligne
2. **Programme Suivi 12 semaines** ⭐ Conseillé — accompagnement complet (centre, inchangé)
3. **Suivi Programme** — séances de suivi dans le cadre du programme 12 semaines

Lien Cal.com de la 3e carte : `/suivi` (slug modifié directement dans le dashboard Cal.com par Vince).

---

## 🐛 Problèmes techniques rencontrés et résolus

Aucun — session propre.

---

## 📋 État actuel du projet (fin session 7)

### Fichiers modifiés ce commit
- `index.html` — 7 modifications
- `mentions-legales.html` — 1 modification

### État des sections du site
- 🟢 Hero : rotation 9s
- 🟢 Offres : nouvelle grille (Ponctuelle / Programme 12s ⭐ / Suivi Programme)
- 🟢 Méthode étape 2 : texte mis à jour
- 🟢 À propos : titre et intro reformulés
- 🟢 Contact / Mentions légales : localisation → Eghezée

---

## 🚀 Prochaines étapes (session 8)

1. **Icônes SVG sur-mesure** — génération via Gemini + intégration
2. **Branchement repo sur Vercel** + désactivation GitHub Pages
3. **Google Business Profile** en mode zone de service
4. **Bascule Cal.com** sur le compte définitif de Michèle

---

*Fin de session 7 — Bonne continuation ! 🌿*

---

# Session 8 — 12 mai 2026
## Mise en production + Google Business Profile + SEO technique

---

## 🎯 Objectifs de la session
1. Mettre `nutrisoins.be` en production sur Vercel
2. Créer et configurer Google Business Profile
3. Compléter le SEO technique du site

---

## 🚀 Mise en production Vercel

### Contexte
- Le projet Vercel `project-coach` héberge déjà le chat IA d'onboarding → ne pas toucher
- Nouveau projet Vercel créé pour le site vitrine
- Adresse de facturation Vercel complétée par Vince avant la session

### Étapes réalisées
1. Nouveau projet Vercel créé → import repo `ChronoNyx/nutrisoins`
2. Framework preset : **"Other"** (HTML statique)
3. Domaine `nutrisoins.be` + `www.nutrisoins.be` connecté → Valid instantanément
4. GitHub Pages désactivé (Settings → Pages → Source : None)

---

## 📍 Google Business Profile

### Création du compte Google
- Adresse créée : `nutrisoins.be@gmail.com`
- Compte dédié NUTRISOINS (pas le compte personnel de Vince)
- Objectif futur : basculer sur `michele@nutrisoins.be` via Google Workspace

### Configuration de la fiche
| Champ | Valeur |
|-------|--------|
| Nom | Nutrisoins |
| Catégorie | Coach personnel pour femmes |
| Adresse | Masquée (domicile) |
| Zone de service | Éghezée + Namur + Belgique |
| Téléphone | Non renseigné (pas de numéro pro) |
| Site web | `nutrisoins.be` |
| Logo | `logo_nutrisoins.svg` converti en PNG 500x500 |
| Description | Texte SEO optimisé (voir ci-dessous) |

### Description Google Business (749 caractères)
> Coach en nutrition certifiée à Éghezée, région de Namur, j'accompagne essentiellement les femmes qui souhaitent retrouver un équilibre alimentaire durable — sans régimes punitifs ni culpabilité. Mon engagement est né d'une conviction profonde : bien manger ne devrait pas être une source de stress. Formée par le réseau Newtrition Coach, j'ai acquis les outils pour vous aider à construire une relation sereine et durable avec la nourriture. Mon approche est bienveillante, progressive et toujours adaptée à votre réalité du quotidien. Parce que le meilleur programme de coaching nutritionnel, c'est celui que vous pouvez tenir sur le long terme.

### Horaires configurés
| Jour | Horaires |
|------|----------|
| Lun, Mar, Jeu | 17:00 – 20:00 |
| Mer | 16:00 – 20:00 |
| Ven | 16:00 – 19:00 |
| Sam | 10:00 – 13:00 / 14:00 – 18:00 |

---

## 🔧 SEO technique

### Schema.org LocalBusiness — mis à jour
Modifications apportées au bloc existant dans `index.html` :
- ✅ Adresse précise "Waret-la-Chaussée" supprimée → "Éghezée"
- ✅ `areaServed` étendu : Éghezée + Namur
- ✅ Horaires ajoutés (`openingHoursSpecification`)
- ✅ Lien Cal.com ajouté (`makesOffer`)
- ✅ Mention périménopause/ménopause ajoutée dans la description

### Nouveaux fichiers créés
- `sitemap.xml` — liste les 3 pages du site avec priorités
- `robots.txt` — `Allow: /` + référence au sitemap

### Google Search Console
- Propriété `https://nutrisoins.be` créée (méthode : balise HTML)
- Balise de vérification ajoutée dans `<head>` de `index.html`
- Sitemap soumis → état **"Opération effectuée"**, 3 pages découvertes

---

## 📦 Commits de la session

```
git commit -m "SEO : Schema.org mis à jour — horaires, zone, périménopause"
git commit -m "SEO : ajout sitemap.xml et robots.txt"
git commit -m "SEO : balise vérification Google Search Console"
```

---

## 🐛 Problèmes rencontrés et résolus

| # | Problème | Solution |
|---|----------|----------|
| 1 | Adresse précise visible publiquement sur Google Business | Masquée + zone de service configurée |
| 2 | Numéro de téléphone personnel affiché | Supprimé |
| 3 | Catégorie "Coach particulier" inadaptée | Remplacée par "Coach personnel pour femmes" |
| 4 | Sitemap "impossible de récupérer" | Délai Vercel — résolu après 2-3 min |

---

## 📋 État actuel du projet (fin session 8)

### Fichiers modifiés
- `index.html` — Schema.org + balise Search Console
- `sitemap.xml` — nouveau
- `robots.txt` — nouveau

### Nouveaux outils actifs
- 🟢 Vercel — déploiement auto sur push `main`
- 🟢 Google Business Profile — fiche active (`nutrisoins.be@gmail.com`)
- 🟢 Google Search Console — validée, sitemap soumis

---

## 🚀 Prochaines étapes (session 9)

1. **Bascule Cal.com** sur le compte définitif de Michèle
2. **Numéro BCE** à mettre à jour dans `mentions-legales.html`
3. **Photo de Michèle** sur la fiche Google si elle accepte
4. **Numéro de téléphone pro** quand disponible
5. **Vérifier attributs `alt`** sur les images du site
6. **Icônes SVG sur-mesure** (Gemini)

---

*Fin de session 8 — Bonne continuation ! 🌿*

---

# Session 9 — 14 mai 2026
## Ajustement SEO snippet Google + refonte du favicon

---

## 🎯 Objectifs de la session

1. Recalibrer le snippet affiché par Google sur les requêtes génériques (ne plus mentionner la périménopause/ménopause par défaut)
2. Préserver le SEO sur les requêtes ciblées (femmes 40+, ménopause)
3. Remplacer le favicon SVG inline par des fichiers PNG/ICO compatibles Google Search
4. Améliorer la lisibilité du favicon aux petites tailles (16/32px)

---

## 🔍 Contexte SEO

Observation initiale (recherche Google "coach nutrition Eghezée") :
- Nutrisoins remonte en **2ème page** après seulement quelques jours en ligne — bon début
- **Mais** le snippet affiché reprend la spécialisation ménopause de manière trop frontale :
  > "Coach en nutrition à Namur. Michèle accompagne les femmes, spécialement 40 ans et plus et en périménopause/ménopause, vers un équilibre alimentaire durable."
- Cible souhaitée : message généraliste accueillant qui n'exclut pas les femmes plus jeunes, tout en restant trouvable sur les requêtes "coach ménopause Namur"

### Diagnostic technique
- Le snippet correspond mot pour mot à la `<meta name="description">` actuelle
- Schema.org `description` contenait aussi la mention ménopause
- Le **corps de la page** était lui parfaitement généraliste — c'est uniquement la balise meta qui surspécialisait
- Stratégie : meta description généraliste + Schema.org structuré (généraliste puis spécialisé) + ajout d'un paragraphe ciblé dans "À propos" pour conserver le SEO sur les requêtes ménopause

---

## ✅ Modifications SEO

### `index.html` — Meta description

**Avant :**
```html
<meta name="description" content="Coach en nutrition à Namur. Michèle accompagne les femmes, spécialement 40 ans et plus et en périménopause/ménopause, vers un équilibre alimentaire durable. En présentiel et en ligne.">
```

**Après :**
```html
<meta name="description" content="Coach en nutrition à Eghezée (Namur). Michèle accompagne les femmes vers un équilibre alimentaire durable — sans régimes punitifs ni culpabilité. Consultations en présentiel ou en ligne.">
```

**Justifications :**
- "Coach en nutrition à **Eghezée (Namur)**" → cible la recherche locale prioritaire (Eghezée) en gardant Namur visible
- "accompagne les **femmes**" → conserve le ciblage genre sans surspécialiser
- "**sans régimes punitifs ni culpabilité**" → met en avant la promesse de marque, plus engageant que la formulation générique précédente
- **158 caractères** → ne sera pas tronquée par Google
- Plus de mention ménopause → la femme de 30 ans qui cherche un coach ne se sent pas exclue

### `index.html` — Schema.org `description`

Le champ a été **gardé tel quel** (structure généraliste → spécialisé), avec une seule correction de vocabulaire demandée par Michèle :
- "Coach en nutrition **bienveillante**" → "Coach en nutrition **et bien-être**"

La mention ménopause reste dans ce champ : Google peut ainsi piocher la version pertinente selon la requête (généraliste pour les requêtes larges, spécialisée pour les rich results ciblés).

### `index.html` — Section "À propos"

Ajout d'un nouveau paragraphe entre le 1er et le 2e paragraphe existants :

> "J'accompagne particulièrement les femmes de 40 ans et plus, notamment en périménopause et ménopause, période où le corps change et où l'alimentation joue un rôle clé pour retrouver énergie, équilibre et sérénité."

**Objectif :** fournir à Google une vraie phrase exploitable comme snippet pour les requêtes ciblées ("coach ménopause Namur", "nutrition périménopause"). Ainsi on conserve le SEO sur ces requêtes à forte intention de conversion sans pour autant les imposer dans le snippet par défaut.

### Google Search Console — réindexation demandée

- Première tentative immédiate : message "Traitement des données en cours, veuillez réessayer dans un jour environ" (URL trop fraîche dans la console)
- Reportée au lendemain — le sitemap pousse aussi le crawl automatiquement
- **Délai estimé avant nouveau snippet visible :** 3 à 14 jours

---

## 🎨 Refonte du favicon

### Problème identifié

Google Search affichait un globe gris générique à côté du résultat `nutrisoins.be` au lieu du logo. Cause : le favicon était un **SVG inline en data-URI** (encodé dans l'attribut `href` du `<link rel="icon">`).

Google ne lit pas toujours correctement les favicons SVG en data-URI — il préfère des **fichiers physiques** (PNG/ICO) accessibles à des URLs propres.

### Solution mise en place

Génération d'un **set complet de favicons physiques** depuis le SVG du logo lotus, en plusieurs tailles couvrant tous les usages :

| Fichier | Taille | Usage |
|---------|--------|-------|
| `favicon.ico` | multi (16/32/48) | Compatibilité Google Search + vieux navigateurs |
| `favicon-16.png` | 16x16 | Onglets, barre de favoris |
| `favicon-32.png` | 32x32 | Onglets HD, raccourcis bureau |
| `favicon-192.png` | 192x192 | Android Chrome |
| `favicon-512.png` | 512x512 | **Recommandé par Google Search** |
| `apple-touch-icon.png` | 180x180 | iOS (écran d'accueil) |

### Itération sur les couleurs

Première version générée : **cercle ocre `#B56A3A` + lotus blanc + point ocre** (identique au header du site).

**Problème constaté visuellement** : à 32px et 16px, les traits fins du lotus blanc se perdaient sur l'ocre — contraste insuffisant.

**Test comparatif** : génération de 7 combinaisons de couleurs issues de la palette du site, avec analyse à 16px et 32px.

**Version retenue (#04) :**
- 🟫 Fond crème (`#FDFBF8`)
- 🌿 Lotus vert olive (`#3E4B31`)
- 🟠 Point chakra ocre (`#B56A3A`) — conserve l'accent de marque

Ce choix maximise la lisibilité à toutes les tailles (gros contraste fond clair / lotus très foncé), reste 100% dans la palette du site et améliore l'accessibilité.

### Mise à jour du HTML

**Avant** (1 ligne très longue avec SVG inline encodé) :
```html
<link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg ...">
```

**Après** (6 lignes propres, fichiers physiques) :
```html
<link rel="icon" type="image/x-icon" href="/favicon.ico">
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32.png">
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16.png">
<link rel="icon" type="image/png" sizes="192x192" href="/favicon-192.png">
<link rel="icon" type="image/png" sizes="512x512" href="/favicon-512.png">
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
```

**Note importante** : `logo_nutrisoins.svg` est **conservé** dans le repo — il sert toujours pour le header du site, la confirmation du formulaire et la section À propos. Le favicon est une déclinaison distincte.

---

## 🐛 Problèmes rencontrés et résolus

| # | Problème | Solution |
|---|----------|----------|
| 1 | Search Console : pas de bouton "Demander une indexation" | URL trop fraîche dans la console — attendre 24h, le sitemap déclenche aussi le crawl |
| 2 | Favicon blanc sur ocre peu lisible à 16/32px | Comparaison de 7 combinaisons → choix de vert olive sur crème |
| 3 | Après push des favicons, l'ancien favicon restait visible | `index.html` n'avait pas été poussé (seuls les nouveaux PNG l'avaient été) — diagnostiqué via `git status` |

---

## 📦 Commits de la session

```
git commit -m "SEO: meta description généraliste + ajout expertise 40+/ménopause dans À propos"
git commit -m "Favicon: remplacement SVG inline par fichiers PNG/ICO multi-résolutions (compatible Google Search)"
git commit -m "Favicon: nouvelle version vert olive sur fond crème (meilleure lisibilité à 16/32px)"
git commit -m "Favicon: bascule HTML vers fichiers PNG/ICO + maj journal"
```

---

## 📋 État actuel du projet (fin session 9)

### Fichiers modifiés / ajoutés
- `index.html` — meta description, Schema.org `description`, paragraphe À propos, balises favicon
- `favicon.ico` — nouveau
- `favicon-16.png` — nouveau
- `favicon-32.png` — nouveau
- `favicon-192.png` — nouveau
- `favicon-512.png` — nouveau
- `apple-touch-icon.png` — nouveau
- `journal_de_bord.md` — session 9 ajoutée
- `journal_condense.md` — synchronisé

### Snippet Google attendu (sous 3-14 jours)
> **Coach en nutrition à Eghezée (Namur)**
> *Michèle accompagne les femmes vers un équilibre alimentaire durable — sans régimes punitifs ni culpabilité. Consultations en présentiel ou en ligne.*

### Favicon visible (immédiat sur navigateur après vidage cache, 1-4 semaines pour Google Search)
Lotus vert olive sur cercle crème avec point chakra ocre.

---

## 🚀 Prochaines étapes (session 10)

1. **Vérifier le nouveau snippet Google** sur "coach nutrition Eghezée" (sous 2 semaines)
2. **Vérifier l'apparition** sur "coach nutrition ménopause Namur" ou similaires
3. **Bascule Cal.com** sur le compte définitif de Michèle
4. **Numéro BCE** à mettre à jour dans `mentions-legales.html` dès réception
5. **Photo de Michèle** sur la fiche Google si elle accepte
6. **Numéro de téléphone pro** quand disponible
7. **Vérifier attributs `alt`** sur les images du site
8. **Icônes SVG sur-mesure** (Gemini)

---

*Fin de session 9 — Bonne continuation ! 🌿*

---

# Session 10 — 15 mai 2026
## Diagnostic global du site + Sprint 1 (corrections de surface) + Sprint 2 (analytics) + audit Facebook

---

## 🎯 Objectifs de la session

1. Conduire un **diagnostic global** du site (technique, UX, SEO, conversion, business)
2. Exécuter le **Sprint 1** — corrections de surface urgentes
3. Exécuter le **Sprint 2** — installation analytics + audit Facebook
4. Cartographier les améliorations restantes par ordre d'impact

---

## 🔍 Diagnostic global — synthèse

Analyse complète du repo + site live + paysage concurrentiel local. Le site est **propre, professionnel et au-dessus de la moyenne** des coachs solos belges — les 9 sessions précédentes se voient. Les leviers identifiés sont des **optimisations** de niveau supérieur, pas des correctifs critiques.

Diagnostic organisé en **6 niveaux d'urgence/impact**, avec un plan d'action en 5 sprints. Le détail complet est dans le `journal_condense.md`.

---

## ✅ Sprint 1 — Corrections de surface (faites cette session)

### Bugs et incohérences corrigés dans `index.html`

| # | Zone | Avant | Après |
|---|---|---|---|
| 1 | Schema.org `makesOffer.url` | `cal.com/vincent-qxx86o` | `cal.com/nutrisoins` |
| 2 | CTA hero principal | `cal.com/vincent-qxx86o` | `cal.com/nutrisoins` |
| 3 | Hero rotatif slot 3 | `J'adapte  mon` (double espace) | `J'adapte mon` |
| 4 | Offre Ponctuelle | `Bilan partiel` (ambigu) | `Mise au point ciblée` |
| 5 | Offre Programme | `présenciel` | `présentiel` |
| 6 | H2 À propos | `Je m'appelle Michèle,` (cassé sémantiquement) | `Je m'appelle Michèle — coach en nutrition à Eghezée` |
| 7 | À propos para 1 | `j'accompagne essentiellement les femmes` | `j'accompagne principalement les femmes` |
| 8 | Footer copyright | `© 2025` | `© 2026` |

La modif #6 glisse un **mot-clé local dans un H2** — bénéfice SEO secondaire au-delà de la simple correction sémantique.

La bascule des liens Cal.com de `vincent-qxx86o` (compte test) vers `nutrisoins` (compte de production) **finalise un des chantiers en attente depuis la session 4**.

---

## ✅ Sprint 2 — Analytics + audit Facebook (faits cette session)

### Installation de Cloudflare Web Analytics

**Outil choisi :** Cloudflare Web Analytics (gratuit à vie, sans cookies, sans bandeau RGPD requis).

**Comparaison réalisée** entre Cloudflare, Umami self-hosted (Vercel + Postgres) et Plausible (~9€/mois). Cloudflare retenu pour : coût zéro, install 5 min, pas de DB à gérer, données essentielles couvertes (trafic, sources, devices, pays). Si besoin d'events custom plus tard, Umami peut s'ajouter à côté sans casser Cloudflare.

**Compte créé** sur dash.cloudflare.com avec l'adresse `nutrisoins.be@gmail.com` (même que Google Business). Site `nutrisoins.be` ajouté en mode "Manually add a site" puisque le DNS reste chez OVH.

**Token généré :** `8d81dd2ad83443f589fc4e85743e0654`

**Snippet injecté** dans les 3 pages HTML (`index.html`, `mentions-legales.html`, `politique-confidentialite.html`), juste avant `</body>` :

```html
<!-- Cloudflare Web Analytics -->
<script defer src='https://static.cloudflareinsights.com/beacon.min.js' data-cf-beacon='{"token": "8d81dd2ad83443f589fc4e85743e0654"}'></script>
<!-- End Cloudflare Web Analytics -->
```

### Mise à jour `politique-confidentialite.html` — conformité RGPD

La politique RGPD a été enrichie pour mentionner Cloudflare Web Analytics :

- **§2 (notice-box)** : reformulée — "Aucune donnée d'identification n'est collectée à votre insu. Une mesure d'audience anonyme et agrégée est mise en œuvre via Cloudflare Web Analytics (voir section 8)."
- **§7 (Cookies)** : clarifié — "aucun cookie" reste exact (Cloudflare n'en pose pas)
- **§8 NOUVEAU** : section dédiée à Cloudflare Web Analytics, détaillant les 4 critères d'exemption de consentement (pas de cookie, pas d'IP stockée, pas d'identifiant unique, données agrégées). Référence aux lignes directrices CEPD/CNIL/APD pour les outils de mesure d'audience anonymes. Lien vers la politique Cloudflare.
- **§8/9/10 renumérotés en §9/10/11**

Le site reste **sans bandeau cookies** — le traitement Cloudflare Web Analytics est exempté de consentement préalable car strictement anonyme.

### Refonte du footer (icon Facebook + retrait Instagram)

Dans `index.html`, section `.footer-social` :

**Avant :**
```html
<a href="...instagram...">📷</a>
<a href="...facebook...">📘</a>
```

**Après :**
```html
<a href="https://www.facebook.com/profile.php?id=61589545773180" ...>
    <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
        <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 ..."/>
    </svg>
</a>
```

- **Instagram retiré** — Michèle ne maîtrise pas l'outil, lien actif vers profil non alimenté = anti-conversion
- **Facebook conservé** — 4 publications, Michèle maîtrise l'outil, c'est son canal social principal
- **Emoji 📘 remplacé par SVG officiel Facebook** — hérite de `currentColor` (gris doux par défaut, blanc sur fond ocre au hover, comportement géré par le CSS existant)
- **`aria-label`** ajouté pour l'accessibilité

### Audit de la page Facebook NUTRISOINS

**Accès constaté (capture Meta Business Suite) :** Vince a un **accès partiel** à la page — peut publier, répondre aux messages, voir les stats, mais **ne peut pas** modifier le nom, la catégorie, l'adresse, ni gérer les autres utilisateurs.

**État actuel de la page observé :**
- Nom : "Michèle Renault - Nutrisoins - Newtrition Coach"
- 38 followers, 4 publications, page active (post du 11 mai)
- Catégorie : "Coach personnel" ✅
- Description courte : OK, fidèle à l'esprit du site
- 3 langues déclarées : FR/EN/NL
- ⚠️ **Adresse personnelle de Michèle affichée** : "rue des bruyeres 256, 5310" (fuite de vie privée)
- ⚠️ "Habite à Namur" affiché (info perso inutile)
- ⚠️ Nom de page non conforme aux décisions du journal ("Michèle" uniquement) + risque d'usurpation marque Newtrition
- ⚠️ URL en chiffres `profile.php?id=...` au lieu d'un handle propre

**Mémo de réglages élaboré** (catégories, nom de page, handle `@nutrisoins`, zone de service, photo de couverture, bouton CTA, etc.) avec discussion des 3 options pour le nom :
- A. `NUTRISOINS` (simple, zéro risque)
- B. `NUTRISOINS — Coach Newtrition à Eghezée` (recommandée)
- C. `Michèle Renault - Nutrisoins - Newtrition Coach` (risque marque + vie privée)

**Décision (utilisateur)** : *"Le nécessaire a été fait avec Michèle"* — le sujet Facebook est **sorti du backlog actif**. Ne pas le rouvrir spontanément dans les sessions futures. La page reste avec un accès partiel pour Vince.

### Mini-formation "positionnement local Facebook"

Explication des 3 leviers SEO local (catégorie / zone géographique / cohérence NAP entre site, Google Business, Facebook). Évoqué que la page tierce `OkHoreca` (autre projet de Vince, contrôle total) peut servir de bac à sable pour s'entraîner sur les mêmes interfaces.

---

## 📊 Méthodologie de session — leçon apprise

**Friction constatée** : Claude a eu tendance à enchainer plusieurs sujets en parallèle (Cal.com + Instagram + réglages Facebook + Sprint 3), ce qui a généré deux interruptions explicites (`STOP`, `pas à pas`).

**Convention retenue pour les sessions futures :**
- Une seule action à la fois
- Attendre confirmation avant de passer à la suivante
- Éviter les fenêtres de choix multiples répétitives (l'utilisateur préfère la conversation libre)
- Si une décision est prise ("on gèle X"), ne pas la rouvrir sans demande explicite

---

## 📁 Commits de la session

```
git commit -m "fix: corrections diverses (Cal.com, fautes orthographe, H2 SEO, footer 2026)"
git commit -m "feat: ajout Cloudflare Web Analytics + mise à jour politique RGPD"
git commit -m "feat: Cloudflare Web Analytics + footer FB propre (Instagram retiré, icône SVG officielle)"
```

*Note : selon le rythme de push de Vince, ces commits peuvent être regroupés en 1 ou 2 push.*

---

## 📋 État actuel du projet (fin session 10)

### Fichiers modifiés cette session
- `index.html` — Sprint 1 (8 corrections) + Cloudflare snippet + footer FB (Instagram retiré, icône SVG)
- `mentions-legales.html` — Cloudflare snippet
- `politique-confidentialite.html` — Cloudflare snippet + réécriture §2/§7 + nouveau §8 + renumérotation

### Outils actifs
- 🟢 Vercel — déploiement auto sur push `main`
- 🟢 Google Business Profile (`nutrisoins.be@gmail.com`)
- 🟢 Google Search Console
- 🟢 **Cloudflare Web Analytics** (NOUVEAU) — token `8d81dd2ad83443f589fc4e85743e0654`
- 🟡 Cal.com basculé sur compte `nutrisoins` (dans le code, côté dashboard Cal.com à vérifier)
- 🟢 Facebook page (accès partiel Vince) — sujet fermé côté backlog actif

### Diagnostic global — chantiers cartographiés

Le diagnostic complet a identifié environ **30 améliorations** réparties en 5 sprints. Le détail complet et l'ordre de priorité sont dans le `journal_condense.md` — section "Backlog d'améliorations identifiées".

---

## 🚫 Sujets fermés explicitement côté utilisateur

- **Facebook (réglages page)** : "Le nécessaire a été fait avec Michèle". Ne pas relancer.
- **Instagram** : compte fermé / Michèle ne maîtrise pas — retiré du footer. Ne pas relancer.

---

## 🚀 Prochaines étapes (session 11)

Au choix selon l'envie/disponibilité de l'utilisateur — par ordre d'impact identifié :

1. **Sprint 3 — Conversion** : afficher les prix + hiérarchiser les CTA + personnaliser confirmation formulaire
2. **Sprint 4 — SEO renforcé** : section Ménopause + FAQ Schema.org + réintégrer périménopause dans meta description
3. **Sprint 5 — Expansion** : 1er article de blog + pages dédiées par offre + icônes SVG Gemini

**Backlog opérationnel** (peuvent être traités isolément) :
- Numéro BCE à mettre à jour dans `mentions-legales.html` dès réception
- Photo de Michèle sur fiche Google Business si elle accepte
- Numéro de téléphone pro quand disponible
- Google Workspace + adresse `michele@nutrisoins.be` (~6€/mois)
- Vérifier nouveau snippet Google sur "coach nutrition Eghezée" (suite session 9)
- Vérifier la 1ère visite dans Cloudflare Web Analytics (sous 24-48h après push)

---

*Fin de session 10 — Bonne continuation ! 🌿*
