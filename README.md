# Outils Miweb

Outils autonomes pour le traitement des contenus numériques.

---

## Extracteur de diapositives vidéo

**Fichier** : `extracteur-slides-video.html`

**Site public** : https://alexandra-guiderdoni.github.io/extracteur-images-frames-video/extracteur-slides-video.html

Extrait automatiquement les diapositives uniques d'une vidéo au format JPG. Traitement 100 % local (Canvas API), aucune donnée envoyée.

### Fonctionnalités

- Détection automatique des changements de slides par comparaison pixel
- Paramètres ajustables (intervalle, seuil de similarité, qualité JPG)
- Téléchargement individuel ou ZIP
- Accordéon pédagogique expliquant les paramètres
- Pause/reprise du traitement

### Alignement DSFR et accessibilité

- **DSFR** 1.14.4 (Design System de l'État)
- **Accessibilité** : structure de titres, landmarks, labels, fieldset, liens d'évitement, ARIA et régions live pris en compte
- **Audit RGAA complet** : non réalisé
- **Sécurité** : CSP meta, SRI sur les ressources CDN, construction DOM programmatique (pas de innerHTML), `'use strict'`

### Utilisation

1. Ouvrir `extracteur-slides-video.html` dans un navigateur (Chrome recommandé)
2. Charger une vidéo par glisser-déposer ou en cliquant sur la zone d'upload
3. Ajuster les paramètres si besoin (voir ci-dessous)
4. Cliquer sur **Extraire**
5. Parcourir les résultats et télécharger les images individuellement ou en ZIP

Fonctionne en `file://` (ouverture directe) ou servi en HTTP.

### Paramètres

| Paramètre | Valeur par défaut | Plage | Description |
|-----------|-------------------|-------|-------------|
| **Intervalle** | 2 s | 0,5 – 10 s | Fréquence d'échantillonnage de la vidéo. Une image est capturée toutes les N secondes. Réduire pour ne rater aucune diapositive courte, augmenter pour accélérer le traitement. |
| **Seuil de similarité** | 99 % | 50 – 99 % | Pourcentage de ressemblance au-dessus duquel deux images consécutives sont considérées identiques et filtrées. À 99 %, seuls les quasi-doublons sont éliminés. Abaisser vers 85–90 % si trop de doublons subsistent. |
| **Qualité JPG** | 90 % | 60 – 100 % | Taux de compression des images extraites. 90 % offre un bon compromis qualité/poids. Monter à 100 % pour un rendu impeccable, descendre vers 70 % pour des fichiers plus légers. |

**Conseils selon le type de vidéo :**

- **Présentation classique** (slides fixes) : intervalle 5 s, seuil 95 %, qualité 90 %
- **Tutoriel avec transitions rapides** : intervalle 1 s, seuil 90 %, qualité 90 %
- **Vidéo longue (> 30 min)** : intervalle 3–5 s, seuil 95 %, qualité 85 % (réduit le temps de traitement et la mémoire)

## Auteurs

- Miweb
