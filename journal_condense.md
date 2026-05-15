# 📋 NUTRISOIN — Journal condensé

> **Note de lecture pour Claude :** ce document est la mémoire de travail du projet. Il contient les décisions structurantes, l'état des chantiers et les conventions adoptées. Pour le détail technique d'une session passée (bugs résolus, code précis), consulter `journal_de_bord.md` dans `C:\nutrisoins\`.
>
> **Dernière mise à jour :** fin de session 10 — 15 mai 2026

---

## 🎯 Le projet en 3 lignes

**NUTRISOINS** est le site vitrine de Michèle Renault-Demptinne, coach en nutrition indépendante à titre complémentaire à Eghezée (région de Namur, Belgique). Activité encadrée par le réseau Newtrition Coach. Une activité de nutrithérapie viendra plus tard, en cours de formation. Le projet est porté techniquement par Vince (compagnon de Michèle).

---

## 🏗️ Architecture technique actuelle

### Stack
- **Site vitrine** : HTML/CSS/JS statique, un seul fichier `index.html` + 2 pages légales
- **Hébergement** : Vercel — `nutrisoins.be` en production (déploiement auto sur push `main`)
- **Repo** : `ChronoNyx/nutrisoins` (public, branche `main`)
- **Workflow** : édition locale via Filesystem → `git push` → déploiement auto
- **Prise de RDV** : Cal.com — compte `nutrisoins` (basculé en session 10)
- **Formulaire** : Formspree (endpoint `xrejjlqz`, destination `renault.demptinne@gmail.com`)
- **Analytics** : Cloudflare Web Analytics (token `8d81dd2ad83443f589fc4e85743e0654`)

### Fichiers du repo (`C:\nutrisoins\`)
```
├── index.html                       ← Site principal
├── mentions-legales.html            ← Page légale
├── politique-confidentialite.html   ← Page RGPD (mention Cloudflare en §8)
├── sitemap.xml                      ← Sitemap soumis à Google Search Console
├── robots.txt                       ← Instructions robots Google
├── coach-nutrition-namur.jpg        ← Photo profil (nom SEO-friendly, anonymisé)
├── logo_nutrisoins.svg              ← Logo lotus (header, accusé envoi, À propos)
├── Image_newtricoach.svg            ← Logo réseau (autorisation obtenue)
├── favicon.ico                      ← Favicon multi-résolution
├── favicon-16.png                   ← Favicon 16x16
├── favicon-32.png                   ← Favicon 32x32
├── favicon-192.png                  ← Favicon Android
├── favicon-512.png                  ← Favicon Google Search
├── apple-touch-icon.png             ← Favicon iOS (180x180)
├── journal_de_bord.md               ← Archive détaillée
└── README.md
```

### Projet secondaire (`C:\nutrisoins_ia\`)
Chat IA d'onboarding des futurs clients (React + Vite + Supabase Edge Function). Code propre mais **à refondre plus tard** (charte graphique non alignée, prompt système à revoir, page admin Michèle à créer). Hébergé sur Vercel sous le projet `project-coach`.

---

## 🎨 Identité visuelle

### Palette (variables CSS — ne pas modifier sans raison)
| Variable | Hex | Usage |
|----------|-----|-------|
| `--vert-olive` | `#3E4B31` | Couleur principale, titres, header |
| `--vert-clair` | `#5a6b45` | Hover des CTA verts |
| `--ocre` | `#B56A3A` | Couleur accent, CTA primaires, logo |
| `--ocre-clair` | `#c97d4e` | Hover des CTA ocre |
| `--fond-creme` | `#FDFBF8` | Fond principal |
| `--fond-beige` | `#F5F0E8` | Fond alternatif sections |
| `--texte` | `#2C1F0E` | Texte principal |
| `--texte-doux` | `#5a4a38` | Texte secondaire |

### Typographies
- **Playfair Display** (serif italique disponible) → titres
- **Lato** (300, 400, 700) → corps de texte

### Logo & favicon
- **Logo principal** (`logo_nutrisoins.svg`) : silhouette en lotus avec point ocre central (chakra). Version blanche sur ocre. Utilisé : header du site, confirmation d'envoi du formulaire, section À propos.
- **Favicon** (PNG/ICO multi-résolutions) : même lotus mais en **vert olive sur fond crème** avec point chakra ocre.

---

## 🛡️ Données personnelles & protection

### Décisions verrouillées
- **Nom affiché** : "Michèle" uniquement (jamais "Michèle Renault" ni "Renault-Demptinne" sur le site public)
- **Adresse** : "Eghezée (à 15 min de Namur)" — pas d'adresse précise (domicile)
- **Téléphone** : non affiché (envisager numéro pro dédié plus tard)
- **Photo** : fichier nommé `coach-nutrition-namur.jpg` (neutre, bonus SEO)
- **Webmaster (Vince)** : n'apparaît jamais sur le site public
- **Google Business** : adresse précise masquée, zone de service configurée

### À remettre en prod
- 📌 **Numéro BCE** : actuellement "en cours d'attribution" dans `mentions-legales.html` — à mettre à jour dès réception

---

## ⚖️ Cadre légal & déontologique

### Belgique — secteur santé/bien-être
- **Coaching nutritionnel ≠ acte médical** : disclaimer obligatoire ("ne remplace pas une consultation médicale")
- **BCE obligatoire** sur le site dès activité active (AR 22 février 2006 + Code droit économique Livre III)
- **RGPD** : politique de confidentialité en place, conforme (responsable, base légale, droits, APD, traitement Cloudflare détaillé en §8)
- **Aucun cookie de tracking** sur le site, **pas de bandeau requis** (Cloudflare Web Analytics est anonyme et exempt de consentement préalable selon CEPD/CNIL/APD)

### Réseau Newtrition Coach
- Logo et nom utilisables avec autorisation expresse obtenue
- L'activité de coaching s'exerce dans le cadre du réseau (formation certifiante, protocole)
- En cas de doute sur ce que le réseau autorise (com, tarifs, zones), recommander vérification directe

### Nutrithérapie
- En cours de formation — **ne pas promouvoir** avant qu'elle soit légalement exerçable
- À intégrer dans la marque ombrelle NUTRISOIN plus tard

---

## 🔧 Conventions techniques

### Git / PowerShell
- **`&&` non supporté** en PowerShell : toujours séparer `git add`, `git commit`, `git push` en commandes distinctes
- Workflow standard : édition via Filesystem → 3 commandes Git séparées dans le terminal

### Édition de fichiers
- **Préférer `edit_file`** pour les modifications ponctuelles
- **`write_file` pour la réécriture complète** d'un fichier (utile quand de gros blocs sont touchés ou en cas de doublons à nettoyer)
- Toujours lire avant d'éditer pour avoir le texte exact

### Formulaire de contact
- Soumission via `fetch` natif vers Formspree (pas de lib externe)
- Destination email modifiable dans le dashboard Formspree sans toucher au code
- Champ honeypot `_gotcha` invisible pour filtrer les bots
- Confirmation de succès avec le logo NUTRISOINS (pas d'emoji générique)

### Méthode de travail attendue (apprise en session 10)
- **Une action à la fois.** Pas d'enchaînement de sujets en parallèle.
- **Attendre confirmation** avant de passer à l'étape suivante.
- **Éviter les fenêtres de choix multiples** répétitives — conversation libre préférée.
- **Si l'utilisateur dit STOP ou "on gèle X"**, ne pas le rouvrir sans demande explicite.

---

## 📊 État des chantiers

### ✅ Terminés
- [x] Site vitrine complet et responsive (sessions 1-3)
- [x] Protection des données personnelles de Michèle (session 2)
- [x] Prise de RDV Cal.com avec 4 types d'événements (session 4)
- [x] Domaine `nutrisoins.be` configuré côté DNS (session 5)
- [x] Formulaire de contact fonctionnel (Formspree) (session 6)
- [x] Mentions légales et politique RGPD (session 6)
- [x] Logo Newtrition autorisé et intégré (session 6)
- [x] Corrections Michèle session 7 (offres réorganisées, textes, Eghezée, rotation 9s)
- [x] Mise en production sur Vercel + désactivation GitHub Pages (session 8)
- [x] Google Business Profile créé et configuré — `nutrisoins.be@gmail.com` (session 8)
- [x] SEO technique : Schema.org, sitemap.xml, robots.txt, Google Search Console (session 8)
- [x] Recalibrage snippet Google (meta description généraliste, paragraphe ciblé À propos) (session 9)
- [x] Refonte favicon : PNG/ICO multi-résolutions, version vert olive sur crème (session 9)
- [x] **Diagnostic global du site** : technique, UX, SEO, conversion, business (session 10)
- [x] **Sprint 1 — corrections de surface** : 8 bugs/incohérences corrigés (session 10)
- [x] **Bascule Cal.com sur compte `nutrisoins`** dans le code (session 10)
- [x] **Cloudflare Web Analytics** installé sur les 3 pages, politique RGPD à jour (session 10)
- [x] **Footer** : Instagram retiré, icône Facebook SVG officielle (session 10)
- [x] **Audit page Facebook** + mémo de réglages (session 10) — *sujet fermé côté utilisateur*

### 🟡 Backlog opérationnel
- [ ] **Numéro BCE** à mettre à jour dans `mentions-legales.html` dès réception
- [ ] **Photo de Michèle** sur la fiche Google Business si elle accepte
- [ ] **Numéro de téléphone pro** à ajouter sur la fiche Google et le site
- [ ] **Google Workspace** + adresse `michele@nutrisoins.be` (~6€/mois)
- [ ] **Vérifier nouveau snippet Google** sur "coach nutrition Eghezée" (suite session 9)
- [ ] **Vérifier la 1ère visite dans Cloudflare Web Analytics** (24-48h après le push de session 10)
- [ ] **Vérifier côté dashboard Cal.com** que le compte `nutrisoins` est bien actif avec les 3 event types (`seance-ponctuelle`, `bilan-initial`, `suivi`)

---

## 🎯 Backlog d'améliorations identifiées (diagnostic session 10)

Classé par sprint, du plus rentable au plus accessoire. Le détail complet du diagnostic est dans `journal_de_bord.md` session 10.

### 🚀 Sprint 3 — Conversion (impact immédiat sur le taux de réservation)
- [ ] **Afficher des prix** (ou fourchettes) sur les 3 cartes d'offres — actuellement "Sur demande" = frein massif à la conversion. Décision tarifaire à prendre avec Michèle.
- [ ] **Hiérarchiser les 2 CTA** (Cal.com direct vs Formulaire) avec une mini-phrase d'aide sous chaque
- [ ] **Personnaliser le message de confirmation** du formulaire (utiliser le prénom)
- [ ] **Schema.org `priceRange`** : retirer "Sur demande" (Google ne l'accepte pas) ou remplacer par fourchette numérique

### 🔍 Sprint 4 — SEO renforcé (impact 3-6 mois)
- [ ] **Section "Périménopause & ménopause"** dédiée entre Méthode et Offres — captation forte sur niche locale peu concurrentielle
- [ ] **Section FAQ avec Schema.org `FAQPage`** (5-6 questions : tarifs, durée résultats, remboursement, différence avec diététicien, ménopause, consultations en ligne)
- [ ] **Réintégrer "périménopause" dans la meta description** (version équilibrée évoquée en diagnostic)
- [ ] **Bandeau d'accent ménopause** dans le hero ou un sous-titre rotatif dédié
- [ ] **Compléter `lastmod`** dans `sitemap.xml` à chaque modif importante

### 📈 Sprint 5 — Expansion (impact long terme)
- [ ] **Premier article de blog** : "Ménopause et alimentation : que manger pour retrouver son équilibre" (cible niche locale)
- [ ] **Pages dédiées par offre** : au moins `/coaching-menopause` pour multiplier la surface SEO
- [ ] **Icônes SVG sur-mesure** (Gemini) pour remplacer les emojis 🌿🎓🤝📍✉️💻⭐🌱🌾
- [ ] **Récolte progressive des témoignages** : protocole de demande après chaque accompagnement programme

### 🛠️ Technique & UX (à intégrer dans les sprints au fur et à mesure)
- [ ] **`loading="lazy"` + `width`/`height`** sur les images (sauf hero) pour le CLS
- [ ] **`<link rel="preconnect">`** pour Google Fonts (gain LCP)
- [ ] **Optimiser `coach-nutrition-namur.jpg`** en `.webp` (cible 80-120 Ko)
- [ ] **Sortir le CSS en `style.css`** quand de nouvelles pages s'ajoutent
- [ ] **Respecter `prefers-reduced-motion`** sur les animations (hero rotatif + scroll reveal)
- [ ] **IntersectionObserver defensive coding** : ne pas masquer les éléments via JS si JS échoue
- [ ] **Ajouter "Contact" dans la navigation** principale
- [ ] **Reformuler la phrase passive** de la section Identification ("Si vous vous retrouvez…" → "Si l'une de ces phrases résonne en vous…")

### 💼 Stratégie commerciale (long terme)
- [ ] **Tarifs définitifs** à arrêter avec Michèle
- [ ] **Partenariats locaux** quand activité plus mature (pharmacies, kinés, ostéopathes, sages-femmes, salles de sport)
- [ ] **Cal.com embedded en iframe** pour mesurer le funnel complet (V2)
- [ ] **Lancement de l'activité nutrithérapie** (quand formation finalisée)

### 🔵 Refonte du chat IA d'onboarding (`C:\nutrisoins_ia`)
- [ ] Revue du prompt système de l'IA
- [ ] Harmonisation graphique avec la charte du site
- [ ] Page admin pour Michèle (consultation des résumés, gestion des tokens)
- [ ] Workflow d'envoi automatique du lien après réservation Cal.com

---

## 🚫 Sujets fermés explicitement (ne pas rouvrir spontanément)

- **Facebook** : "Le nécessaire a été fait avec Michèle" (session 10). Page configurée avec Michèle hors session. Ne pas reproposer de réglages.
- **Instagram** : Michèle ne maîtrise pas l'outil. Lien retiré du footer en session 10. Ne pas reproposer.

---

## 🗂️ Grille des offres actuelle

| Position | Offre | Durée | Mode | Slug Cal.com |
|----------|-------|-------|------|--------------|
| Gauche | **Séance Ponctuelle** | / séance | Présentiel ou en ligne | `seance-ponctuelle` |
| Centre ⭐ | **Programme Suivi 12 semaines** | / 12 semaines | Présentiel uniquement | `bilan-initial` |
| Droite | **Suivi Programme** | / séance de suivi | Présentiel uniquement | `suivi` |

> La séance découverte a été supprimée de la grille à la demande de Michèle (session 7).

---

## 🌐 SEO — État actuel

### Technique (en place)
- ✅ Balises `<title>` et `<meta description>` optimisées (généralistes, sans surspécialisation ménopause)
- ✅ Open Graph configuré (partage réseaux sociaux)
- ✅ Schema.org LocalBusiness complet (horaires, zone, périménopause/ménopause dans description structurée)
- ✅ Paragraphe dédié "femmes 40+/périménopause/ménopause" dans la section À propos
- ✅ `sitemap.xml` soumis à Google Search Console
- ✅ `robots.txt` en place
- ✅ Favicon PNG/ICO multi-résolutions
- ✅ **Mot-clé local "Eghezée" dans un H2** de la section À propos (session 10)
- ✅ **Analytics actifs** (Cloudflare Web Analytics)

### Snippet Google attendu (sous 3-14 jours après session 9)
> **Coach en nutrition à Eghezée (Namur)**
> *Michèle accompagne les femmes vers un équilibre alimentaire durable — sans régimes punitifs ni culpabilité. Consultations en présentiel ou en ligne.*

### Google Business Profile
- ✅ Fiche active — catégorie "Coach personnel pour femmes"
- ✅ Zone de service : Éghezée + Namur + Belgique
- ✅ Adresse masquée
- ✅ Horaires configurés
- ✅ Description SEO (749 caractères, mention périménopause/ménopause)
- ⏳ Photo de Michèle — en attente de validation par elle

### Leviers SEO en attente (Sprint 4)
- [ ] Section dédiée ménopause + FAQ Schema.org → captation forte sur niche locale
- [ ] Premier article de blog → indexer du contenu long sur "ménopause prise de poids alimentation"
- [ ] Pages dédiées par offre → multiplier la surface de captation

---

## 🎯 Brief de génération d'icônes (pour Gemini, à utiliser au Sprint 5)

```
Je dois générer un set d'icônes SVG pour un site de coaching en nutrition.

CONTRAINTES CRÉATIVES IMPÉRATIVES :
- Style : line-icons minimalistes, traits fins (stroke-width 1.5 à 2)
- Forme : carrées sur viewBox 24x24, sans remplissage (outline uniquement)
- Couleur unique : #B56A3A (ocre) — pas de dégradé, pas de couleur secondaire
- Ambiance : organique, naturelle, douce (en cohérence avec un logo en lotus stylisé)
- Coins arrondis : stroke-linecap="round", stroke-linejoin="round"

LISTE DES ICÔNES À PRODUIRE :
1. Écoute / oreille attentive
2. Diplôme / certification
3. Mains qui se serrent / accompagnement
4. Pousse / jeune plante (offre découverte)
5. Feuille / branche d'olivier (offre programme)
6. Épi de blé (offre ponctuelle)
7. Localisation / point sur carte
8. Email / enveloppe
9. Écran / vidéo (consultation en ligne)
10. Étoile (badge "conseillé")

LIVRABLE :
Code SVG de chaque icône, prêt à coller en inline dans du HTML.
```

---

## 🛠️ Outils & connecteurs

- **Filesystem** : accès à `C:\nutrisoins`, `C:\nutrisoins_ia` (+ autres dossiers non liés au projet)
- **GitHub** : repo `ChronoNyx/nutrisoins`
- **Cal.com** : compte `nutrisoins` (basculé en session 10, à vérifier côté dashboard)
- **Formspree** : endpoint `xrejjlqz`
- **Vercel** : site vitrine en prod sur `nutrisoins.be` + projet `project-coach` (chat IA)
- **DNS** : zone OVH (records email préservés pour future `@nutrisoins.be`)
- **Google Business Profile** : compte `nutrisoins.be@gmail.com` — fiche active
- **Google Search Console** : propriété `https://nutrisoins.be` validée, sitemap soumis
- **Cloudflare Web Analytics** : compte `nutrisoins.be@gmail.com`, site `nutrisoins.be`, token `8d81dd2ad83443f589fc4e85743e0654`

---

## 💡 Style de travail attendu

- **Proactif** : faire la réflexion stratégique avant de produire si elle est nécessaire
- **Concis** : livrables directement utilisables, pas de blabla
- **Honnête** : signaler les zones d'incertitude (réseau Newtrition, budget, etc.)
- **Pédagogue** : ne pas supposer de compétences techniques avancées chez Vince
- **Adapté aux moyens** : solutions gratuites ou peu coûteuses sauf indication contraire
- **Langue** : français par défaut
- **Pas à pas** : une action à la fois, attendre confirmation avant la suivante

---

*Fin du condensé — synchronisé avec `journal_de_bord.md` session 10*
