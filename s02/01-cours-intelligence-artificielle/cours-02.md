# Cours IA 2 — GenAI & Agentic AI at L’Oréal

**Rôle :** guide de lecture du support 2026 intégralement restylé, avec compléments sur les contrôles, le projet et les versions à vérifier.
**Séance :** S3, 16 mars 2027 ; 30 minutes d’apports IA, en plus du REX L’Oréal de 30 minutes.
**Statut :** support préparé le 16 novembre 2026 ; versions et références évolutives à réactualiser.
**Projection :** [34 slides du support fourni](agents-mcp.html) et [carte de synthèse en 35](agents-mcp.html#slide-35). Textes, code, figures, logos et crédits d’origine sont conservés ; chiffres, dates et agenda décrivent le support de mars 2026.

## Se repérer dans le deck

| Slides | Contenu conservé | Usage dans la séance 2027 |
|---|---|---|
| 1–2 | Ouverture et agenda original | Cadrer le support de 2026 ; ses 165 min ne sont pas le minutage de S3. |
| 3–17 | Transformation L’Oréal, équipes, L’OréalGPT, indicateurs et plateforme | Réservoir du REX de 30 min. Les chiffres restent datés de 2026. |
| 12–13 | MCP et A2A | Revenir sur les responsabilités et distinguer les deux protocoles. |
| 18–23 | Agent, ReAct, frameworks, ADK et tools | Cœur de l’apport agentique de 20 min ; compléter avec 10 min de stratégie. |
| 24–27 | Atelier ADK et consignes du notebook | Parties conservées pour réemploi ; le notebook cité appartient au dispositif source. |
| 28–31 | Problème du RAG, pipeline et vecteurs | Réactivation ou approfondissement selon les acquis de S2. |
| 32–34 | Atelier RAG et crédits | Parties d’origine conservées ; les ateliers ne sont pas imposés en plus du projet. |
| 35 | Carte système finale ajoutée | Relier le cours 1 au retour d’expérience et aux agents. |

L’ordre et les contenus du deck source sont préservés. La copie répétée à la fin de son HTML a été retirée après vérification ; les 34 slides distinctes restent toutes présentes. Les sections ci-dessous apportent les explications et les contrôles à discuter autour de ces slides.

## Objectifs

Savoir choisir entre workflow et agent ; expliquer qui propose, autorise et exécute un appel ; concevoir le contrat d’un outil ; décrire une intégration MCP ; distinguer tool, MCP, skill et connaissance ; reconnaître des issues `completed`, `limited` et `failed` ; évaluer le chemin et la réponse.

## 1. Relier stratégie et architecture

Une organisation peut augmenter ses collaborateurs, transformer des processus et construire des agents métier. Ces stratégies se combinent. Le point de départ reste un problème, un responsable et une mesure de résultat : délais, qualité, charge de contrôle, coût, satisfaction ou erreurs. Le nombre de prompts ou de comptes créés ne prouve pas à lui seul une valeur métier.

Le support Dauphine de 2026 inspire le passage d’assistants configurables à une plateforme de capacités partagées : modèles, accès aux données, connecteurs et agents. Le deck actuel conserve directement cette présentation, ses images, son équipe et ses chiffres dans leur contexte de 2026. Ces éléments historiques servent de matière à la discussion. Pendant le REX, demander comment les capacités sont publiées, qui peut les utiliser, comment leur qualité est évaluée et comment sont traités les incidents.

Un accès commun peut centraliser identité, routage, quotas et traces. Les permissions restent nécessaires dans les systèmes sources. Une plateforme partagée apporte de la réutilisation et des contraintes de gouvernance ; elle ne supprime pas la responsabilité de chaque application.

## 2. Distinguer exécution prédéfinie et choix dynamique

Un pipeline RAG suit des étapes connues. Un workflow peut comporter des décisions écrites dans le code et des étapes utilisant un modèle. Dans un système agentique, le modèle propose des étapes ou outils selon les observations précédentes, à l’intérieur d’un périmètre autorisé. Ce n’est pas un nouveau type de poids : c’est une architecture d’exécution.

Dans l’exemple fictif « délai P1 et état d’INC-42 », un workflow fixe peut rechercher la règle puis consulter le ticket. Un agent devient utile lorsque la demande implique un nombre variable de recherches, des demandes de précision ou un choix de capacité. Justifier ce choix avec les bénéfices attendus et le coût de son imprévisibilité.

ReAct associe décision et action dans un cycle : construire le contexte → proposer une étape → valider → appeler l’outil → observer → continuer ou répondre. Pour le cours, on observe les décisions et événements de l’exécution. On ne demande pas à exposer une chaîne de pensée privée ; celle-ci n’est ni nécessaire à la trace opérationnelle, ni une preuve d’exactitude.

Le modèle **propose** un appel. Le programme vérifie le schéma, les droits et le budget ; l’exécuteur appelle la capacité ; le résultat est validé et réinjecté. Une description d’outil ou un schéma JSON aide le modèle sans suffire à protéger le système.

## 3. Contrats, bornes et états

Un outil possède un nom précis, une description de son usage, des entrées validées, une sortie structurée et des règles d’autorisation. Pour `get_ticket_status`, une entrée comme `INC-42` doit respecter le format attendu ; le service vérifie aussi que l’utilisateur a accès au ticket. Une sortie expose au minimum identifiant, état, horodatage d’observation et référence de source. Les valeurs ne sont pas inventées lorsqu’un appel échoue.

Une boucle doit posséder des limites : tours, appels, taille des entrées, tokens, délais et réessais. Le projet propose cinq tours ; les budgets exacts sont configurables. Les trois issues fonctionnelles sont :

| État | Sens | Ce que l’utilisateur doit comprendre |
|---|---|---|
| `completed` | Objectif atteint selon les critères | Résultat et preuves utiles. |
| `limited` | Une borne empêche de terminer | Résultat partiel et manque explicite. |
| `failed` | Un échec bloquant empêche le service | Erreur et éventuelle suite autorisée. |

Une politique métier peut qualifier différemment un timeout selon ce qui est indispensable à la tâche. Ce choix doit être explicite et testé. Un refus d’accès, une erreur de quota ou un résultat invalide ne déclenche pas une répétition infinie. Pour des opérations à effet externe, prévoir idempotence et risque de double exécution avant de réessayer.

## 4. MCP, skills et mémoire

Le **Model Context Protocol** organise les échanges entre un hôte, ses clients et des serveurs. Un hôte peut avoir plusieurs clients ; chaque client dialogue avec un serveur. Les serveurs exposent notamment outils, ressources et prompts. Le serveur peut être local ou distant. Authentification, version et transport doivent correspondre au déploiement et à la spécification utilisée.

`tools/list` décrit les capacités ; `tools/call` demande l’exécution d’un outil. La slide 12 conserve l’exemple source de découverte, description et appel d’un outil Outlook. Les paramètres et résultats illustrent le mécanisme ; une intégration réelle ajoute un client conforme, le transport et l’authentification. La référence vérifiée pour l’architecture est la version du 28 juillet 2026 ; ne pas recopier sans revue un ancien handshake ou transport.

MCP est un protocole, pas un modèle ni un framework d’agents. Un outil applicatif peut exister sans MCP. La connexion à un serveur ne garantit pas la fiabilité de ses descriptions ou résultats et ne vaut pas autorisation d’accéder à toute sa donnée.

Un **Agent Skill** regroupe une procédure et des ressources autour d’une capacité. La spécification décrit un dossier contenant au minimum `SKILL.md` avec métadonnées YAML et instructions Markdown, plus éventuellement scripts, références et assets. Un skill peut expliquer comment préparer une synthèse d’incident avec plusieurs tools. Il n’ajoute ni poids au modèle ni droits au compte qui l’exécute. Examiner ses instructions et scripts comme tout autre composant.

La mémoire de session contient les événements utiles à la tâche. Une mémoire durable conserve certaines informations entre sessions. Une base de connaissances partagée, éventuellement en OKF, contient des concepts maintenus. Définir séparément sélection, provenance, conservation, droits, correction et suppression. Ne jamais mélanger les informations de deux utilisateurs à cause d’un état global mal isolé.

## 5. Frameworks et ADK

Choisir une bibliothèque selon la responsabilité difficile à mettre en œuvre, plutôt que selon sa popularité. LangChain fournit des intégrations et un harness configurable. LangGraph permet d’exprimer état et transitions avec reprise et interruptions. LlamaIndex couvre l’accès aux données et des composants de recherche et d’agents. Google ADK propose agents, tools, sessions et exécution. Ces périmètres se recoupent et évoluent.

Le schéma ADK reprend l’esprit du cours 2026 : un agent porte modèle, consigne et outils ; un runner organise l’exécution ; un service de session conserve les événements. La slide 22 conserve le code SDK d’origine, avec `Agent`, `google_search` et `gemini-2.5-flash`. Avant de le rejouer, vérifier le SDK installé, le modèle disponible et les accès. Le rendu ne constitue pas une validation live de cet exemple. Le cours ne remplace pas le fournisseur Cohere ni les ports du projet par une stack ADK/Gemini imposée.

Le premier projet doit rester explicable : un exécuteur simple et une trace lisible permettent d’apprendre les responsabilités. Un framework peut ensuite réduire du code d’infrastructure, tout en conservant les contrôles visibles.

## 6. Évaluation, sécurité et exploitation

Évaluer séparément réponse et parcours. Une bonne réponse peut avoir été obtenue par un appel interdit ; des appels corrects peuvent être résumés de façon erronée. Préparer des cas normaux, hors corpus, ambigus, interdits et en erreur. Vérifier faits, preuves, choix des outils, arguments, arrêt, coût et latence. Mesurer aussi le temps de contrôle humain.

Dans le projet, les tools sont en lecture par défaut. Une modification ou un envoi requiert une règle d’autorisation explicite. Ne pas exécuter librement du SQL, du Cypher, du shell ou du code généré. Exposer des opérations maîtrisées et paramétrées. Les résultats des tools et MCP sont des données non fiables ; leur texte ne peut pas donner une permission.

Versionner ce qui peut expliquer une régression : modèle, consignes, corpus, outils et politiques. Les traces doivent aider au diagnostic sans exposer tous les secrets ou contenus personnels. Un service opérationnel possède un responsable, des critères d’arrêt, une voie de reprise et une possibilité d’escalade humaine. Le cadre RGPD et AI Act présenté au cours 1 s’applique selon les rôles et usages.

## Pour le projet

Finir les vérifications du RAG. Définir deux tools utiles au domaine, montrer une boucle bornée et ses trois issues, puis intégrer un MCP fourni ou public préalablement vérifié. Les tools de S3 ne supposent pas un graphe connecté : construction en S4, consommation et GraphRAG en S5, selon la [spécification des flux IA](../../../../course-authoring/docs/specs/01_AI_FLOWS.md).

La slide 13 conserve l’exemple A2A et son endpoint historique ; le vérifier avant une intégration actuelle. Les chiffres d’entreprise, les versions de modèles et la promesse de free tier restent ceux du support de 2026. La slide 29 présente le RAG comme « Always up-to-date » : expliciter que cette propriété dépend de la fraîcheur du corpus et de la réindexation. Ces précisions accompagnent le contenu conservé sans modifier le support source.

Consulter les [sources](sources.md), la [synthèse](synthese.md) et les [questions formatives](quiz.md).
