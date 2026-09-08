# Yahya Piano — site vitrine & réservation

Site vitrine pour Yahya AHAJI, professeur de solfège et piano, avec réservation en ligne et back-office admin.

## Structure

```
index.html        page unique (HTML + CSS + JS, sans dépendance externe hors polices Google)
videos/            5 clips de démonstration (mp4) + vignettes (jpg)
assets/portrait.jpg  photo de profil
```

## Utiliser le site

Ouvrez simplement `index.html` dans un navigateur, ou hébergez le dossier tel quel (GitHub Pages, Netlify, n'importe quel hébergement statique).

## Fonctionnalités

- Sélecteur de langue FR / EN / ES / AR (l'arabe passe le site en RTL)
- Bouton mode sombre en forme de touche de piano
- Réservation : niveau (Initiation / Intermédiaire, 350 DH/h chacun), calendrier, créneaux horaires, confirmation par WhatsApp
- Espace administrateur cliente : calendrier avec les réservations du jour, création/modification/suppression, blocage de journées entières
- Données de réservation stockées via l'API `window.storage` (Claude Artifacts) — si le site est hébergé ailleurs qu'en artefact Claude, cette persistance devra être remplacée par un vrai backend (voir "Limites" ci-dessous)

## Accès admin

Le lien public a été retiré. Pour y accéder, ajoutez `#admin` à l'URL, par exemple :

```
https://votre-domaine.com/#admin
```

Mot de passe par défaut : `yahya2026` — à changer directement dans `index.html` (chercher `ADMIN_PASSWORD`).

## Limites connues

- **Stockage des réservations** : le site utilise `window.storage`, une API disponible uniquement dans les artefacts Claude. Si vous hébergez ce site ailleurs (GitHub Pages, un serveur classique...), les réservations ne seront pas sauvegardées tant qu'un vrai backend (base de données + API) n'aura pas remplacé cette partie.
- **Notifications par e-mail** : non automatisées. Chaque réservation ouvre WhatsApp avec les détails pré-remplis pour prévenir Yahya en temps réel.
- **Icône WhatsApp** : dessinée à la main pour rester fidèle au logo officiel.

## Personnalisation rapide

- Numéro WhatsApp : variable `WA_NUMBER` dans `index.html`
- Mot de passe admin : variable `ADMIN_PASSWORD` dans `index.html`
- Créneaux horaires proposés : tableau `DAILY_SLOTS` dans `index.html`
- Tarifs et niveaux : tableau `LEVELS` dans `index.html`
