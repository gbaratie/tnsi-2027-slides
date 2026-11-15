# Manifeste des assets — cours IoT

Date de préparation : 8 novembre 2026. Les fichiers sont conservés localement pour que le deck reste utilisable hors ligne.

## Photographies

| Fichier | Usage | Auteur / source | Licence et page source | Traitement |
|---|---|---|---|---|
| `photos/factory-robot.jpg` | Couverture et preuve industrielle | Homa Appliances | [Unsplash — sz1CHL7Pky0](https://unsplash.com/photos/blue-industrial-robot-arm-in-factory-sz1CHL7Pky0), licence Unsplash | Recadrage panoramique, voile marine |
| `photos/circuit-board.jpg` | Anatomie d'un objet connecté | Harrison Broadbent | [Unsplash — 1mu9gF8OhNk](https://unsplash.com/photos/1mu9gF8OhNk), licence Unsplash | Recadrage 16:9, contraste froid |
| `photos/maintenance-technician.jpg` | Métiers et exploitation | Sten Rademaker | [Unsplash — UZUzvJEvKnI](https://unsplash.com/photos/UZUzvJEvKnI), licence Unsplash | Recadrage vertical, voile marine |
| `photos/satellite-earth.jpg` | Transition satellite | NASA | [Unsplash — yZygONrUBe8](https://unsplash.com/photos/yZygONrUBe8), licence Unsplash | Recadrage plein cadre, vignette |

La licence Unsplash autorise l'utilisation gratuite des photos, y compris commercialement, sans attribution obligatoire ; les crédits sont néanmoins conservés pour la traçabilité : <https://unsplash.com/license>.

## Logos

Les marques restent la propriété de leurs détenteurs. Les logos sont utilisés uniquement pour identifier les acteurs dans une cartographie pédagogique, sans modification de proportions ni de couleurs.

Révision du 11 novembre 2026 : la carte regroupe plusieurs entreprises dans six familles (capteurs, radios/modules, passerelles, réseaux, plateformes, solutions industrielles), toutes visibles simultanément. Les logos existants sont réutilisés sans nouvel artwork ; chaque nom renvoie à la page officielle de l’entreprise. La carte décrit des capacités et des rôles pouvant se recouvrir, sans classement ni parts de marché.

| Fichier | Source | Notes |
|---|---|---|
| `logos/stmicroelectronics.svg` | [Simple Icons](https://simpleicons.org/?q=STMicroelectronics) | Marque STMicroelectronics |
| `logos/orange.svg` | [Simple Icons](https://simpleicons.org/?q=Orange) | Marque Orange |
| `logos/amazonwebservices.svg` | [AWS / Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Amazon_Web_Services_Logo.svg) | Artwork AWS, fichier SVG local |
| `logos/schneiderelectric.svg` | [Simple Icons](https://simpleicons.org/?q=Schneider%20Electric) | Marque Schneider Electric |
| `logos/veolia.svg` | [Veolia / Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Veolia_logo.svg) | Artwork Veolia, fichier SVG local |

## Icônes

Les SVG du dossier `icons/` proviennent de [Lucide](https://lucide.dev/), récupérés le 8 novembre 2026. Licence ISC. Seuls les pictogrammes utilisés ou prévus dans le deck sont conservés localement.

## Ajout du 15 novembre 2026 — standards et maisons connectées

Deux diagrammes originaux intégrés au HTML : pile réseau/application et installation locale d’une lampe fictive. Les pictogrammes sont des repères fonctionnels ; les marques identifient les standards et plateformes sans constituer une recommandation d’achat. Traits et révélations expliquent les relations ; aucune image ne représente un déploiement client.

| Fichier | Diapositive et rôle | Source et droits | Préparation |
|---|---|---|---|
| `logos/matter.svg` | 11 · identifier le standard applicatif | [CSA, page Matter](https://csa-iot.org/all-solutions/matter/) ; [artwork officiel](https://csa-iot.org/wp-content/uploads/2021/12/matter.svg), marque CSA | Fichier officiel inchangé, image embarquée dans le SVG ; proportions et couleurs conservées |
| `logos/thread-built-on.svg` | 11 · identifier le réseau Thread | [Thread Group, présentation](https://threadgroup.org/what-is-thread/overview) ; [badge officiel](https://threadgroup.org/portals/0/svg/TG_BOT-logo_w-g_H.svg), marque Thread Group | Badge « Built on Thread » inchangé, sans affirmation de certification d’un objet réel |
| `logos/apple-home.png` | 12 · identifier Apple Home / l’app Maison | [Apple, Home app](https://www.apple.com/home-app/) ; [icône officielle](https://www.apple.com/v/home-app/n/images/overview/home_icon__fqdsai7nyfma_large.png), marque Apple | Fichier inchangé, proportions et couleurs source ; ne pas reproduire l’interface de l’app |
| `logos/google-home.svg` | 12 · identifier Google Home | [Google Home, Matter et Thread](https://home.google.com/get-inspired/matter-and-thread/) ; [sprite officiel, symbole `logo`](https://home.google.com/static/icons/google-icons.svg?cache=3b26556#logo), marque Google | Symbole extrait dans un SVG autonome ; tracés, couleurs et viewBox conservés |
| `icons/lightbulb.svg`, `icons/router.svg`, `icons/cable.svg` | 11–12 · lampe, routeur et réseau filaire | [Lucide, fichiers source](https://github.com/lucide-icons/lucide/tree/main/icons), licence ISC ; récupération le 15 novembre 2026 | SVG locaux ; même famille et même traitement que les pictogrammes existants |

Ces artworks sont utilisés pour l’identification pédagogique de leurs détenteurs ; aucune licence libre sur les marques n’est présumée. Aucun recadrage, filtre ou changement de couleur des logos. Pas de dépendance réseau à la lecture ; les liens documentaires restent volontairement externes.

## Ressource live

Les fontes partagées [IBM Plex](../../../assets/fonts/plex/manifest.md) remplacent Google Fonts depuis la révision du 11 novembre 2026. Le schéma du parcours d’une mesure est un SVG natif intégré au HTML : capteurs/actionneurs, réseau local, bridge/passerelle, edge, Internet, réception des données et applications ; aucun moteur de rendu externe n’est requis.

`https://satellitemap.space/` reste une démonstration volontairement externe. La diapositive satellite possède une photo locale et un schéma simplifié comme solution de secours.

## Carte récapitulative

| Fichier | Usage et provenance | Préparation |
|---|---|---|
| `infographics/iot-technical-summary.png` | Infographie pédagogique originale générée avec `image_gen.imagegen`, selon les deux références visuelles fournies par l’auteur : fond clair, panneaux techniques, mini-schémas, flux numérotés et légende. Scénario fictif entrepôt/champs ; aucun déploiement client représenté. | 9 novembre 2026 ; 1672×941 px ; textes et schémas intégrés ; fichier inchangé. En projection, l’en-tête est repris en HTML dans les fontes du deck ; panneaux et légende sont conservés. |

L’original généré est conservé ; la copie ci-dessus est locale au deck et s’affiche hors ligne. L’image est une représentation pédagogique relue, pas une preuve technique ou une photographie de système réel. Sa consultation en pleine résolution est accessible par clic sur la slide. Aucun droit sur les références n’est présumé du fait qu’elles ont été fournies ; leurs contenus et marques ne sont pas reproduits dans cette planche IoT.
