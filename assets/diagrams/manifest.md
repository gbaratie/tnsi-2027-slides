# Diagrammes techniques communs

| Fichier | Usage | Production |
|---|---|---|
| [`graphrag-path.svg`](graphrag-path.svg) | Data 26 : domaine S4 → assertions sourcées → projection graphe → parcours borné → contexte GraphRAG | Mermaid **12.3.0**, rendu SVG local le 9 novembre 2026, apparence `classic` sans ombre ; texte SVG, titre et description accessibles ; aucun appel distant requis |

Le schéma décrit une progression de préparation et de sélection du contexte. Les flèches ne sont pas des dépendances de code. Le rendu utilise du texte marine sur les nœuds bleu clair et des liens bleus adaptés au fond marine de la slide. Il ne garantit pas une réponse correcte : les chemins, leurs sources et la comparaison avec RAG seul restent à vérifier.

La finition professionnelle incorpore IBM Plex Sans 400/600 dans le SVG. Le `viewBox`, les coordonnées, les textes, les nœuds et les chemins sont conservés. Les [fontes locales et leurs licences](../fonts/plex/manifest.md) accompagnent le deck ; aucun téléchargement de fonte n'est nécessaire pour cette image SVG.

La palette affinée utilise une surface de nœud `#edf4ff`, une frontière `#526f97` et des connecteurs `#0f62fe`, sans modifier la géométrie. Les traits et les flèches sont vérifiés sur le fond marine du deck.
