# Changelog

## 1.1.0 — 2026-07-17

### Extracteur de diapositives vidéo (`extracteur-slides-video.html`)

#### DSFR et accessibilité
- Mise à niveau des ressources DSFR vers `@gouvfr/dsfr` 1.14.4 avec SRI
- Retrait du bloc marque République française et des formulations publiques non prouvées
- Ajout des favicons DSFR et d'une enveloppe de page plus explicite
- Remplacement des classes locales préfixées `fr-*` par des classes applicatives
- Conservation d'une progression accessible avec `role="progressbar"` sans composant DSFR inventé

#### Nettoyage du dépôt
- Suppression de `LICENSE`
- Suppression de `index.html`
- Suppression de `CLAUDE.md`
- Retrait des liens et sections pointant vers `LICENSE`
- Mise à jour de l'URL publique vers la page HTML directe

## 1.0.0 — 2026-04-02

### Extracteur de diapositives vidéo (`extracteur-slides-video.html`)

**Ajout initial** de l'outil d'extraction de diapositives uniques depuis une vidéo.

#### Fonctionnel
- Extraction par comparaison pixel avec seuil de similarité configurable
- Intervalle d'échantillonnage et qualité JPG ajustables
- Téléchargement individuel ou ZIP (JSZip)
- Pause/reprise du traitement
- Accordéon pédagogique DSFR sur les paramètres
- Alerte DSFR avec métadonnées vidéo (durée, poids, frames estimées)

#### Accessibilité
- DSFR 1.11.2 (header, footer, fieldset, accordion, alertes, grille responsive)
- RGAA 4.1.2 (hiérarchie titres, landmarks, labels, skip links, ARIA live regions)
- WCAG 2.2 AA (contrastes, clavier, lecteur d'écran, progressbar labellisé)
- Construction DOM programmatique (pas de innerHTML)

#### Sécurité
- Content Security Policy (meta)
- Subresource Integrity sur les 4 ressources CDN
- `'use strict'`, objet CONFIG, fonction escapeHTML
- ObjectURL révoquées, garde anti-race-condition, annulation extraction
