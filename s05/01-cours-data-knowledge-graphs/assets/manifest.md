# Ressources — deck Data harmonisé au style Cloud

Harmonisation du 9 novembre 2026. Les images, pictogrammes et fontes sont locaux ; le deck n'effectue aucun chargement de ressources distantes. Les références cliquables et Aura restent des destinations externes intentionnelles.

## Illustration

`illustrations/documents-to-graph.png` · ancienne couverture conservée, hors affichage : illustration éditoriale originale produite avec `image_gen.imagegen`, 1672×941 px. Documents et réseau conceptuels, sans entreprise, système réel ou extraction automatique représentés. Original copié sans modification de pixels ; recadrage 16:9 et voiles marine en CSS pour le titre, l'en-tête et le crédit. Cette illustration ne sert plus de photographie d’ouverture. Prompt et contrôle conservés dans le dossier interne Data.

## Pictogrammes

Famille unique [Lucide](https://lucide.dev/), licence [ISC locale](icons/LICENSE.txt). SVG conservés localement et incorporés inline, sans bibliothèque à l'exécution. Couleur et épaisseur de trait adaptées en CSS ; géométrie conservée. Usage décoratif (`aria-hidden`) à côté des libellés HTML.

| Fichiers | Origine et rôle |
|---|---|
| `database`, `shield-check`, `workflow`, `network` | Copies des SVG déjà sourcés du deck Cloud ; parcours Sources/Curation/Domaine/Graphe et pictogrammes de question. |
| `scan-search` | Copie du SVG déjà sourcé du deck IoT ; retrouver et valider. |
| `table-2`, `file-text`, `braces` | [Lucide, dépôt officiel](https://github.com/lucide-icons/lucide/tree/main/icons), récupérés le 9 novembre 2026 depuis `raw.githubusercontent.com/lucide-icons/lucide/main/icons/<nom>.svg` ; formes structurée/semi-structurée/non structurée et représentations table/document. |

## Synthèses, diagramme et fontes

- Carte Data, cinq vues avec focus, et planche Data Mesh : [manifeste commun](../../../assets/infographics/manifest.md). Les fichiers et leurs pixels sont inchangés ; l'original complet reste accessible au clic.
- Parcours GraphRAG de la mission : [manifeste des diagrammes](../../../assets/diagrams/manifest.md), SVG local inchangé.
- IBM Plex Sans et IBM Plex Mono : [fichiers locaux et licences](../../../assets/fonts/plex/manifest.md). Toute la typographie HTML utilise ces familles ; les textes déjà incorporés aux planches restent rasterisés.

Le scénario Orion, le code et les données du support sont des exemples pédagogiques. Aucun logo de fournisseur n'a été ajouté par cette harmonisation.

## Couverture photographique

La slide 1 utilise `../../assets/photos/analytics-luke-chesser.jpg`, photo Luke Chesser / Unsplash. [Source et licence](../../../assets/photos/manifest.md). Recadrage et voile marine CSS ; ressource locale hors ligne.

Le 11 novembre 2026, l’auteur a retenu un écran de visualisation de données pour remplacer les livres de la couverture. Le récit, les diagrammes et les 28 slides sont conservés.
