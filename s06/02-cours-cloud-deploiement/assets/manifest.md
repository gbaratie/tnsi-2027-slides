# Manifeste des assets — cours Cloud

Préparation : 9 novembre 2026. Les ressources sont conservées localement ; aucun hotlink ni bibliothèque distante n'est nécessaire à la lecture du deck. Les styles et scripts sont embarqués dans `slides.html`.

## Images

| Fichier | Slide / rôle | Provenance, droits et traitement |
|---|---|---|
| `photos/circuit-board.jpg` | 3 · rappeler le matériel physique | Harrison Broadbent, [Unsplash — 1mu9gF8OhNk](https://unsplash.com/photos/1mu9gF8OhNk), [licence Unsplash](https://unsplash.com/license). Copie inchangée de la ressource déjà sourcée du [deck IoT](../../../s04/01-cours-iot-interconnexion/assets/manifest.md), recadrée verticalement par CSS. Photo contextuelle de composants, sans attribution à un datacenter ou fournisseur. |
| `photos/datacenter-illustration.png` | Ancienne couverture conservée, hors affichage | Illustration originale générée avec `image_gen.imagegen`, 1672×941 px. Infrastructure fictive, statut enregistré dans ce manifeste ; aucun fournisseur réel représenté. Original inchangé ; recadrage plein cadre et voile marine CSS. |
| `infographics/cloud-technical-summary.png` | 19 · carte du dépôt au service | Planche pédagogique originale générée avec `image_gen.imagegen`, 1672×941 px, avec la synthèse IoT du dépôt réellement transmise comme référence graphique. Scénario fictif ; aucune architecture de production certifiée. Image inchangée, consultable au clic. Un court connecteur SVG natif complète code → pipeline dans le HTML. |

Les prompts, références, originaux de génération et contrôles sont documentés dans le dossier interne de conception Cloud. Les captures fournies par l'auteur ont guidé le contenu ; leurs images et affirmations non vérifiées ne sont pas reproduites.

L'accès à `images.unsplash.com` était refusé par le proxy à la préparation. Les nouvelles photographies repérées n'ont pas été téléchargées ; la seule photographie retenue est celle déjà disponible et documentée dans le dépôt. L'illustration générée n'est pas attribuée à Unsplash.

## Icônes

Famille unique : [Lucide](https://lucide.dev/), SVG copiés du deck IoT le 9 novembre 2026 : `cloud`, `database`, `cpu`, `network`, `shield-check`, `workflow`, `activity`, `gauge`, `route`, `user-round-cog`. Licence ISC, [notice locale](icons/LICENSE.txt). Les tracés sont conservés ; taille et couleur sont adaptées au contexte. Leur incorporation inline permet d'illustrer fichiers, ressources, flux et responsabilités sans requête réseau.

## Logos

Utilisation descriptive dans la cartographie et les explications d'outils. Les marques appartiennent à leurs détenteurs ; elles ne prouvent ni recommandation, partenariat, qualification, prix ni performance. Proportions et couleurs des SVG source sont conservées ; OpenShift utilise une version monochrome d'origine.

| Fichier | Source de l'artwork |
|---|---|
| `amazonwebservices.svg` | Copie du deck IoT ; [AWS / Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Amazon_Web_Services_Logo.svg). |
| `kubernetes.svg` | [CNCF Artwork officiel](https://github.com/cncf/artwork/blob/main/projects/kubernetes/icon/color/kubernetes-icon-color.svg) ; [conditions locales](logos/LICENSE-cncf.md), renvoyant aux règles de marque Linux Foundation. |
| `docker.svg` | [Devicon — docker-original.svg](https://github.com/devicons/devicon/blob/master/icons/docker/docker-original.svg). |
| `azure.svg` | [Devicon — azure-original.svg](https://github.com/devicons/devicon/blob/master/icons/azure/azure-original.svg). |
| `googlecloud.svg` | [Devicon — googlecloud-original.svg](https://github.com/devicons/devicon/blob/master/icons/googlecloud/googlecloud-original.svg). |
| `terraform.svg` | [Devicon — terraform-original.svg](https://github.com/devicons/devicon/blob/master/icons/terraform/terraform-original.svg). |
| `github.svg` | [Devicon — github-original.svg](https://github.com/devicons/devicon/blob/master/icons/github/github-original.svg). |
| `openshift.svg` | [Simple Icons — redhatopenshift.svg](https://github.com/simple-icons/simple-icons/blob/develop/icons/redhatopenshift.svg). |

Récupération : 9 novembre 2026. Notices des collections conservées : [Devicon, MIT](logos/LICENSE-devicon.txt), [Simple Icons, CC0](logos/LICENSE-simple-icons.md). Ces licences ne suppriment pas les droits de marque des acteurs identifiés.

## Compositions natives et fontes

Les piles physique/VM, le pool cloud, la matrice de responsabilités, les topologies, le cluster, la flotte multicluster, les frontières de données, le pipeline, l'arbre de fichiers et la fenêtre Pages sont des compositions HTML/SVG originales. Objets et flèches décrivent des exemples simplifiés, pas des déploiements clients. Les flux réels sont distingués de la configuration ; deux environnements ne signifient pas une réplication.

IBM Plex Sans 400/500/600/700 et IBM Plex Mono 400 sont chargées depuis les fontes locales partagées sans modification : [provenance et licence OFL 1.1](../../../assets/fonts/plex/manifest.md).

Le canevas fixe 1920×1080 est réduit uniformément. Les fragments au clavier des caractéristiques cloud, pratiques multicloud et termes CI/CD sont complets en mode final, avec réduction des mouvements et à l'impression. Des textes alternatifs accompagnent images, logos et schémas.

## Nouvelle couverture photographique

La slide 1 utilise `../../assets/photos/datacenter-taylor-vick.jpg`, photo Taylor Vick / Unsplash. [Source et licence](../../../assets/photos/manifest.md). La restriction CDN décrite ci-dessus concernait la préparation précédente ; la photographie est désormais téléchargée et livrée localement.
