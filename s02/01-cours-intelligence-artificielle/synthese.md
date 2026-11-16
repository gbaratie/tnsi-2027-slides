# IA — Synthèse des deux cours

**Rôle :** mémo étudiant ; les explications et sources détaillées sont dans [cours 1](cours-01.md), [cours 2](cours-02.md) et le [registre des sources](sources.md).
**Statut :** préparé le 16 novembre 2026 pour S2–S3 de 2027.

## Cours 1 — Du modèle au système

| Notion | À retenir | Erreur à éviter |
|---|---|---|
| FM / LLM | Modèle préentraîné ; le LLM est centré sur le langage. | Confondre le modèle avec l’application. |
| Hébergement | API cloud, infrastructure exploitée ou machine locale. | Réduire la décision au prix par token. |
| Mémoire des poids | Paramètres × bits / 8, puis ajouter les besoins d’exécution. | Croire que 4 Go de poids suffisent dans 4 Go de VRAM. |
| Token | Unité propre à un tokenizer ; pas nécessairement un mot. | Appliquer une conversion mots/tokens universelle. |
| Contexte | Consignes + historique sélectionné + documents + outils + sortie à réserver. | Croire qu’une grande fenêtre garantit une lecture fidèle. |
| Mémoire | L’application stocke puis réinjecte un état sélectionné. | Assimiler historique affiché et historique transmis. |
| Prompt | Tâche, sources, format, contraintes et critères vérifiables. | Confondre éloquence et exactitude. |
| RAG | Retrouver des preuves puis les fournir au modèle. | Considérer une citation existante comme une preuve de fidélité. |
| OCR | Extraire des caractères d’une image ; contrôler chiffres, structure et unités. | Supposer que tout PDF exige de l’OCR. |
| Embedding | Vecteur utilisé pour comparer des représentations compatibles. | Interpréter une proximité comme une vérité. |
| OKF | Connaissances portables en Markdown/YAML et liens, complémentaires du RAG. | Présenter un format émergent comme un remplacement universel. |

Deux flux partagent le même index : **préparer les connaissances** à chaque mise à jour, puis **répondre avec des sources** à chaque question.

Pipeline minimal : **sources → extraction → chunks identifiés → embeddings → index** ; à la question : **recherche autorisée → contexte borné → génération → réponse et sources**. Sans preuve suffisante, signaler la limite ou s’abstenir.

Exemple de budget : `32 000 − 2 000 règles − 6 000 échange − 4 000 sortie = 20 000 tokens` disponibles pour des passages et autres surcoûts. Mesurer les tokens du modèle utilisé.

## Cours 2 — Agir dans un périmètre explicite

| Notion | Rôle |
|---|---|
| Workflow | Les transitions sont définies par le programme. |
| Agent | Le modèle propose des étapes dans un catalogue autorisé. |
| Tool | Opération avec entrées, sorties, validation et permissions. |
| MCP | Protocole pour exposer et consommer outils, ressources et prompts. |
| Skill | Procédure et ressources réutilisables, souvent regroupées dans `SKILL.md`. |
| A2A | Échanges de tâches et résultats entre agents ; approfondissement facultatif. |

Boucle : **contexte → proposition → validation et autorisation → exécution → observation → réponse ou nouveau tour**. Le modèle propose ; le programme autorise et exécute.

Fin observable : `completed` si l’objectif est atteint, `limited` si une borne bloque la suite, `failed` si un échec est bloquant. Borner tours, appels, tokens, délais et réessais. Garder les outils en lecture par défaut et une politique explicite pour les effets externes.

Les frameworks facilitent certaines responsabilités : LangChain (intégrations / harness), LangGraph (état / orchestration), LlamaIndex (données / recherche), Google ADK (agents / tools / sessions). Leurs périmètres se recoupent ; aucun n’assure automatiquement qualité ou sécurité.

## Les questions à poser avant de livrer

1. Quelle source soutient chaque fait, et est-elle actuelle et accessible à cet utilisateur ?
2. Que contient réellement l’appel au modèle ? Où vit la mémoire ?
3. Qui valide et exécute chaque outil ? Quelles bornes arrêtent la boucle ?
4. Comment une erreur, une absence de preuve ou un refus d’accès apparaissent-ils ?
5. Quel gain reste-t-il après contrôle humain, coût et latence ?
6. Quels usages, données, responsabilités et obligations réglementaires sont concernés ?

Le **FDE** construit et déploie avec l’équipe cliente ; le **FDA** relie contexte métier, architecture et mise en œuvre. Ces rôles collaborent avec les spécialistes IA, données et métier ; leurs périmètres dépendent de l’organisation.

Le travail se transforme par tâches ; une mesure d’exposition n’est pas une prévision d’emplois supprimés. Les centres de données ne se réduisent pas à l’IA ; une estimation environnementale doit préciser son périmètre. Un résultat documentaire ou MCP peut contenir une prompt injection : il reste une donnée non fiable.
