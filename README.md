# Portfolio — Mehdi Seghier

Portfolio de BTS SIO option SISR (Iris Campus, Nice), en recherche d'alternance Administrateur Systèmes et Réseaux.

Site statique (HTML / CSS / JS vanilla, sans framework ni backend), hébergé sur GitHub Pages.

## Contenu du portfolio

**Page d'accueil** — présentation, compétences (administration systèmes, réseaux, sécurité, virtualisation,
scripting, support utilisateurs), projets réalisés, aperçu de la veille technologique, formulaire de contact.

**Projets présentés**, chacun cliquable pour voir le détail (captures, extraits de configuration ou de code) :

- **Refonte réseau & serveur Raspberry Pi 5 — stage chez Noha Auto (Cannes)**
- **CRM / Dashboard — Nice Volley-Ball**, développé en binôme (PHP/Slim 4, PostgreSQL, Docker, API Weezevent
  et Brevo)
- **Refonte e-commerce — TechShop**, projet individuel (HTML/CSS/JS, panier, paiement, mode sombre)
- **Santa's Workshop**, outil de suivi de production de cadeaux (JS, localStorage)
- **Sécurisation Pare-feu / VPN**, home-lab personnel sous Debian (UFW, Nginx, MariaDB)
- **Gestion de Parc (GLPI)**, **Déploiement Active Directory**, **Segmentation Réseau (VLAN)**
- **Catalogue et stock — Noha Auto**, application web multi-utilisateurs (Node.js, SQLite, HTTPS via Tailscale Funnel)
- **Scanner réseau en PowerShell**, **Boîte à outils réseau** (calculateur VLSM, TP Wireshark, générateur WireGuard,
  PKI interne OpenSSL, outil Nmap) : projets publics avec tests automatiques

**Tableau de synthèse des réalisations professionnelles** — document officiel BTS SIO (annexe VI-1),
téléchargeable en PDF depuis la page d'accueil.

**Page de veille technologique** — l'impact de l'ordinateur quantique sur le chiffrement des données et la
transition vers la cryptographie post-quantique, avec sommaire cliquable, glossaire et FAQ de préparation à
l'oral.

## Arborescence

```
.
├── index.html                  Page d'accueil
├── veille.html                 Veille technologique : cryptographie post-quantique
├── assets/
│   ├── css/
│   │   ├── styles.css          Styles communs à tout le site
│   │   └── veille.css          Styles spécifiques à la page de veille
│   ├── js/
│   │   ├── script.js           Thème clair/sombre, menu, fond animé, terminal, formulaire...
│   │   ├── veille.js           Sommaire collant, barre de lecture (page veille)
│   │   └── projects-data.js    Détail des projets + logique de la fenêtre modale
│   └── img/
│       └── projects/           Captures et illustrations des projets
├── documents/
│   ├── cv-mehdi-seghier.pdf
│   ├── veille-technologique-pqc.pdf
│   ├── tableau-synthese-bts-sio-sisr-mehdi-seghier.pdf
│   └── source/
│       └── tableau-synthese.html   Source HTML utilisée pour générer le PDF ci-dessus
├── .gitignore
└── README.md
```

## Aperçu en local

Ouvrir `index.html` dans un navigateur, ou servir le dossier avec l'extension **Live Server** de VS Code
(configurée sur le port 5501, voir `.vscode/settings.json`).

## Mettre à jour le tableau de synthèse (PDF)

1. Modifier `documents/source/tableau-synthese.html` (fichier HTML autonome, CSS inline).
2. Régénérer le PDF avec Microsoft Edge en mode headless, depuis la racine du projet :

   ```powershell
   & "C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" --headless --disable-gpu `
     --print-to-pdf="documents\tableau-synthese-bts-sio-sisr-mehdi-seghier.pdf" `
     --no-pdf-header-footer `
     "documents\source\tableau-synthese.html"
   ```

3. Vérifier que le PDF tient sur une seule page avant de le publier.

## Fonctionnalités notables

- Thème clair/sombre mémorisé (`localStorage`), sans flash au chargement.
- Fond animé (réseau de particules en `<canvas>`) présent sur tout le site, réactif à la souris/au tactile,
  désactivé automatiquement si `prefers-reduced-motion` est actif.
- Terminal interactif (bouton en bas à gauche) : `help`, `whoami`, `skills`, `projects`, `contact`, `veille`,
  `cv`, `synthese`, `neofetch`, `ping`, `clear`...
- Fiches-projets cliquables avec fenêtre modale (galerie d'images, extraits de code, compétences mobilisées).
- Formulaire de contact fonctionnel sans backend (ouvre le client mail du visiteur, pré-rempli).
- Page de veille avec sommaire cliquable, sommaire latéral collant, FAQ en accordéon, feuille d'impression dédiée.
- Accessibilité : lien d'évitement, focus visible, `aria-*` sur les éléments interactifs, respect de
  `prefers-reduced-motion`.
