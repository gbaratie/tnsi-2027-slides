# IA — Registre des sources et des mesures

**Rôle :** rendre les chiffres, choix de vocabulaire et liens des deux cours vérifiables.
**Date de consultation :** 16 novembre 2026.
**Statut :** sources primaires consultées pendant la préparation ; les pages dynamiques doivent être revues avant mars 2027.

Les références sont aussi cliquables en bas des slides concernées. Le numéro de slide ci-dessous correspond au fichier du cours, avec un lien direct `#slide-N`.

## Références publiques

### Dartmouth · 1955/1956
[Source primaire](https://www-formal.stanford.edu/jmc/history/dartmouth/dartmouth.html).

Proposition du 31/08/1955 pour l’atelier de l’été 1956 ; frise sélective, sans prétention exhaustive.

Cours 1 : [3](slides.html#slide-3)

### Vaswani et al. · 2017
[Source primaire](https://arxiv.org/abs/1706.03762).

Article de 2017 sur l’architecture Transformer ; jalon de la frise, sans attribuer tous les modèles génératifs à cette seule architecture.

Cours 1 : [3](slides.html#slide-3)

### Lewis et al. · 2020
[Source primaire](https://arxiv.org/abs/2005.11401).

Travail fondateur de 2020. Le pipeline du cours est une explication pédagogique, pas une reproduction de son système expérimental.

Cours 1 : [5](slides.html#slide-5), [21](slides.html#slide-21), [28](slides.html#slide-28), [47](slides.html#slide-47) · Cours 2 : [28](agents-mcp.html#slide-28), [29](agents-mcp.html#slide-29), [30](agents-mcp.html#slide-30), [31](agents-mcp.html#slide-31)

### Yao et al. · ReAct · 2022
[Source primaire](https://arxiv.org/abs/2210.03629).

Travail de recherche sur le cycle décision/action/observation ; aucune promesse de correction ni demande d’exposition d’un raisonnement privé.

Cours 1 : [5](slides.html#slide-5), [47](slides.html#slide-47) · Cours 2 : [19](agents-mcp.html#slide-19), [20](agents-mcp.html#slide-20)

### OpenRouter · usage au 15/11/2026
[Source primaire](https://openrouter.ai/rankings).

Classement par volume de tokens sur OpenRouter, données au 15/11/2026. Les cinq noms de tête sont un instantané de cette plateforme ; aucune part de marché mondiale ni qualité relative n’est déduite.

Cours 1 : [8](slides.html#slide-8)

### Hugging Face · Model Cards
[Source primaire](https://huggingface.co/docs/hub/model-cards).

Model cards : documentation du modèle, licence et limites. La disponibilité de poids ne suffit pas à établir la liberté d’usage.

Cours 1 : [9](slides.html#slide-9), [47](slides.html#slide-47)

### Hugging Face · modèles et tendances
[Source primaire](https://huggingface.co/models?inference_provider=all&sort=trending).

Panorama de familles et de modalités, pas un palmarès universel. Téléchargements, tendances et évaluations sont des métriques différentes.

Cours 1 : [8](slides.html#slide-8)

### Hugging Face · quantification
[Source primaire](https://huggingface.co/docs/transformers/quantization/concept_guide).

Formule de stockage théorique des poids. Le tableau en Go décimaux est calculé, sans marge runtime. Ajouter quantification, cache KV, activations, buffers et concurrence.

Cours 1 : [11](slides.html#slide-11)

### Cohere · API Chat v2
[Source primaire](https://docs.cohere.com/v2/reference/chat).

Structure Chat v2 : tableau de messages et limite de génération. Le code de démonstration utilise command-a-03-2025 selon l’ADR 0006, pas le modèle de tête de la documentation actuelle.

Cours 1 : [12](slides.html#slide-12), [13](slides.html#slide-13), [43](slides.html#slide-43)

### Cohere · Command A
[Source primaire](https://docs.cohere.com/docs/command-a).

Command A 03/2025 : 111B paramètres, contexte annoncé 256k. Exemple stable aligné sur le fournisseur pédagogique ; cela ne signifie pas modèle le plus récent.

Cours 1 : [11](slides.html#slide-11), [19](slides.html#slide-19)

### Command A · configuration Hugging Face
[Source primaire](https://huggingface.co/CohereLabs/c4ai-command-a-03-2025).

La model card précise que le modèle supporte 256k mais que sa configuration Hugging Face est à 128k. La limite déployée dépend aussi du runtime.

Cours 1 : [19](slides.html#slide-19)

### OpenAI · GPT-5 · spécifications
[Source primaire](https://developers.openai.com/api/docs/models/gpt-5).

400 000 tokens de fenêtre totale pour GPT-5, modèle de 2025 utilisé comme repère de capacité ; ne pas le présenter comme dernier modèle sorti.

Cours 1 : [19](slides.html#slide-19)

### OpenAI · tokenizer interactif
[Source primaire](https://platform.openai.com/tokenizer).

Outil de manipulation en ligne. Noter le tokenizer sélectionné ; il peut différer de celui du découpage imprimé.

Cours 1 : [18](slides.html#slide-18), [44](slides.html#slide-44), [47](slides.html#slide-47)

### OpenAI · tokenizer gpt-oss-20b
[Source primaire](https://huggingface.co/openai/gpt-oss-20b/blob/main/tokenizer.json).

Mesure locale le 16/11/2026 : vocabulaire BPE du tokenizer gpt-oss-20b chargé depuis tokenizer.json ; encodage via tiktoken 0.14.0. Les espaces sont préservés. IDs de Bonjour, le monde ! : 45751, 11, 505, 15807, 1073.

Cours 1 : [18](slides.html#slide-18), [44](slides.html#slide-44)

### Liu et al. · Lost in the Middle
[Source primaire](https://arxiv.org/abs/2307.03172).

Observation expérimentale de 2023 sur les modèles étudiés : utilisation du contexte sensible à la position. Ne pas présenter sa courbe comme benchmark de tous les modèles actuels.

Cours 1 : [19](slides.html#slide-19)

### Docling · formats et conversion
[Source primaire](https://docling-project.github.io/docling/usage/supported_formats/).

Source pour les formats et la conversion documentaire. Le cours conserve TXT/Markdown comme chemin principal du premier TP.

Cours 1 : [22](slides.html#slide-22), [46](slides.html#slide-46)

### Docling · moteurs OCR
[Source primaire](https://docling-project.github.io/docling/concepts/OCR/).

Moteurs et intégration à choisir selon langues, matériel et qualité. OCR, parsing structurel et compréhension multimodale ne sont pas équivalents.

Cours 1 : [22](slides.html#slide-22)

### Open Knowledge Format · spécification v0.2
[Source primaire](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/main/SPEC.md).

Spécification v0.2 au moment de lecture. Les slides 30–31 du cours 1 distinguent format et exécution : un outil lit l’index, le concept, puis la référence liée ; l’application sélectionne les preuves pour le contexte. Exemple fictif, complément possible du RAG, sans gain universel revendiqué.

Cours 1 : [30](slides.html#slide-30), [31](slides.html#slide-31), [34](slides.html#slide-34), [48](slides.html#slide-48) · Cours 2 : [35](agents-mcp.html#slide-35)

### Google Cloud · présentation de l’OKF
[Source primaire](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing).

Présentation de la proposition par Google Cloud ; contexte d’émergence. Pour la structure technique, préférer la spécification versionnée.

Cours 1 : [30](slides.html#slide-30)

### LangChain · documentation
[Source primaire](https://docs.langchain.com/oss/python/langchain/overview).

Positionnement vérifié à la lecture ; intégrations et harness. Les contrôles métier restent à construire.

Cours 1 : [32](slides.html#slide-32) · Cours 2 : [21](agents-mcp.html#slide-21)

### LangGraph · documentation
[Source primaire](https://docs.langchain.com/oss/python/langgraph/overview).

Positionnement vérifié à la lecture ; orchestration avec état et contrôle de flux. LangGraph peut être utilisé sans LangChain.

Cours 1 : [32](slides.html#slide-32) · Cours 2 : [21](agents-mcp.html#slide-21)

### LlamaIndex · documentation
[Source primaire](https://developers.llamaindex.ai/python/framework/).

Positionnement vérifié à la lecture ; données, recherche et applications agentiques. Périmètre recouvrant partiellement les autres outils.

Cours 1 : [32](slides.html#slide-32)

### Google ADK · agents
[Source primaire](https://adk.dev/agents/).

La slide 22 du cours 2 reprend le code SDK du support 2026, sans le remplacer par du pseudocode. Modèle, version du SDK et accès sont à vérifier avant exécution. La refonte du support ne change pas le fournisseur du projet.

Cours 1 : [32](slides.html#slide-32) · Cours 2 : [21](agents-mcp.html#slide-21), [22](agents-mcp.html#slide-22), [25](agents-mcp.html#slide-25), [26](agents-mcp.html#slide-26)

### MCP · architecture · 28/07/2026
[Source primaire](https://modelcontextprotocol.io/specification/2026-07-28/architecture).

Architecture de la spécification 2026-07-28. Hôte, clients et serveurs ; outils, ressources et prompts. Le fragment tools/call est simplifié, pas un client complet. Vérifier aussi version, transport et authentification.

Cours 1 : [5](slides.html#slide-5), [33](slides.html#slide-33), [34](slides.html#slide-34), [48](slides.html#slide-48) · Cours 2 : [12](agents-mcp.html#slide-12), [35](agents-mcp.html#slide-35)

### Agent Skills · spécification
[Source primaire](https://agentskills.io/specification).

Dossier avec SKILL.md et métadonnées, instructions et ressources optionnelles. Ne pas confondre procédure, protocole ou droits d’exécution.

Cours 1 : [33](slides.html#slide-33), [34](slides.html#slide-34), [48](slides.html#slide-48) · Cours 2 : [35](agents-mcp.html#slide-35)

### Anthropic · étude du 05/03/2026
[Source primaire](https://www.anthropic.com/research/labor-market-impacts).

Étude du 05/03/2026 : figure 2 originale, capacité théorique et couverture observée des tâches par catégorie professionnelle. Les valeurs 94 % / 33 % de Computer & Math restent des repères du texte. Le graphique est conservé entier ; aucun pourcentage d’emplois supprimés n’en est déduit.

Cours 1 : [35](slides.html#slide-35)

### AIE · Key Questions on Energy and AI · 2026
[Source primaire](https://www.iea.org/reports/key-questions-on-energy-and-ai/executive-summary).

Mise à jour AIE 2026 : environ 485 TWh en 2025 et projection d’environ 950 TWh en 2030, proche de 3 % de la demande mondiale. Ensemble des data centers ; pas empreinte de la seule IA ni mesure par prompt.

Cours 1 : [37](slides.html#slide-37)

### Commission européenne · calendrier AI Act
[Source primaire](https://ai-act-service-desk.ec.europa.eu/en/ai-act/eu-ai-act-implementation-timeline).

Calendrier européen vérifié au 16/11/2026 : repères sélectifs, exceptions et transitions à consulter. Haut risque annexe III au 02/12/2027 et produits réglementés au 02/08/2028 après révision de 2026.

Cours 1 : [38](slides.html#slide-38), [39](slides.html#slide-39)

### Conseil de l’UE · amendement du 29/06/2026
[Source primaire](https://www.consilium.europa.eu/en/press/press-releases/2026/06/29/artificial-intelligence-council-gives-final-green-light-to-simplify-and-streamline-rules/).

Communiqué du Conseil du 29/06/2026 expliquant la révision des échéances de haut risque. Croiser avec le calendrier et les textes applicables avant un déploiement.

Cours 1 : [39](slides.html#slide-39)

### CNIL · IA et RGPD
[Source primaire](https://www.cnil.fr/fr/technologies/intelligence-artificielle-ia).

Source française sur les usages de l’IA et le RGPD. Les obligations dépendent des traitements, données et rôles ; le deck ne réalise pas un audit juridique.

Cours 1 : [38](slides.html#slide-38)

### A2A · documentation officielle
[Source primaire](https://a2a-protocol.org/latest/).

La slide 13 conserve l’exemple A2A et son endpoint historique du support 2026. Cette conservation ne valide pas l’endpoint pour une intégration actuelle ; consulter la version retenue. A2A reste hors exigence de S3.

Cours 2 : [13](agents-mcp.html#slide-13)

### OpenAI · Forward Deployed Engineer
[Source primaire](https://openai.com/careers/forward-deployed-engineer-(fde)-seattle-seattle/).

Fiche de rôle consultée le 16/11/2026 : découverte, conception, intégration, évaluation, déploiement et adoption avec les équipes clientes. La slide présente des missions, sans estimation d’emplois créés.

Cours 1 : [36](slides.html#slide-36)

### IBM · Forward deployed units · 18/06/2026
[Source primaire](https://www.ibm.com/think/insights/forward-deployed-units-ibm-consulting-field-model-scaling-ai-transformation).

Présentation d’un modèle d’équipe IBM : forward-deployed architect, engineer, spécialistes métier et data/applied AI. Elle soutient la distinction pédagogique FDA/FDE ; les périmètres varient selon l’employeur et ne sont pas des catégories réglementaires. Les livrables P1 sont fictifs.

Cours 1 : [36](slides.html#slide-36)

## Source fournie et statut des illustrations

Le cadrage vient de la roadmap, de la carte des contenus, de la pédagogie, des ADR 0005/0006 et des flux IA. Les dates des séances proviennent du [calendrier](../../../CALENDAR.md).

Le cours 2 reprend tout le contenu des 34 slides du HTML 2026 fourni : textes, images, logos, code, crédits, données d’entreprise et agenda. La copie répétée et mal formée dans le fichier a été retirée ; le fichier source reste inchangé. Ces chiffres et versions conservent leur date d’origine. Les notes du cours 2 précisent leur usage dans le parcours S3 de 2027.

Le cas « P1 / INC-42 », les traces de lecture OKF et d’agent, et le nuage vectoriel 2D du cours 1 sont fictifs. La formule de mémoire et le budget de contexte sont des calculs pédagogiques ; le découpage en tokens est une mesure locale. Le radar Anthropic est la figure officielle d’origine, sans recadrage ni reconstruction. Voir les [crédits des visuels](assets/README.md).

## Références de composition

Les frises et roadmaps utilisent des compositions originales inspirées des principes de couloirs, d’axe et de jalons de [ProductPlan](https://www.productplan.com/learn/roadmap-anatomy), et des horizons de [planification Atlassian](https://www.atlassian.com/agile/product-management/roadmaps). Aucun de leurs graphiques commerciaux n’est recopié. Les icônes proviennent de [Lucide](https://lucide.dev/license).

## À réactualiser avant diffusion

Revoir le panorama de modèles et sa période ; disponibilité, contexte et quotas ; versions des frameworks et protocoles ; spécification OKF ; publications sur l’emploi et l’énergie ; échéances réglementaires. Pour le deck 2, garder l’intégrité du document historique et donner les précisions actuelles à l’oral ou dans les notes. Conserver la date et le périmètre de tout chiffre ajouté.
