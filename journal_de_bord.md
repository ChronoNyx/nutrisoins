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
