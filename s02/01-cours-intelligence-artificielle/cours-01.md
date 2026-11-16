# Cours IA 1 — Du modèle au système IA

**Rôle :** notes de cours à lire en complément de la présentation.
**Public :** M2 MIAGE, TNSI, Dauphine–PSL.
**Séance :** S2, 9 mars 2027 ; 65 minutes d’apports IA dans le déroulé documentaire.
**Statut :** support préparé le 16 novembre 2026 ; références évolutives à réactualiser avant diffusion.
**Projection :** [slides 1–42](slides.html), [synthèse finale 48](slides.html#slide-48) ; approfondissements facultatifs 43–47. Les activités d’architecture et le TP gardent leurs créneaux séparés.

## Ce que l’on doit savoir expliquer

À la fin du cours, distinguer modèle et application ; estimer un budget de contexte et de mémoire des poids ; expliquer comment un historique et des sources sont ajoutés à un appel ; décrire l’ingestion et la consultation d’un RAG ; identifier quand un outil est nécessaire ; argumenter les compromis humains, matériels et réglementaires.

La carte système se construit en six états aux slides 6, 12, 20, 28, 34 et 48. Le modèle garde sa position ; chaque retour ajoute les composants qui viennent d’être étudiés. Les états sont imprimables et se comprennent sans animation.

Le fil conducteur est une demande fictive de support informatique : **« Quel délai pour un incident P1 et où en est INC-42 ? »** La procédure courante de l’exemple indique une prise en charge sous 30 minutes. Le statut du ticket doit venir d’un service métier. Ces données et les réponses illustratives sont composées pour le cours ; elles ne proviennent pas d’un système réel.

## 1. Une histoire plus longue que le chat — slides 3–6

La question de l’intelligence des machines précède le terme « intelligence artificielle ». Le projet de Dartmouth, proposé en 1955 pour un atelier en 1956, structure un champ de recherche. Les approches symboliques et les systèmes experts représentent explicitement des règles. L’apprentissage statistique apprend des régularités à partir de données. Le deep learning profite ensuite de corpus plus vastes et d’accélérateurs de calcul. Ces approches continuent à coexister.

Le Transformer de 2017 est un jalon majeur pour les modèles de langage. Le préentraînement à grande échelle, l’adaptation aux instructions et les interfaces conversationnelles ont rendu des modèles généralistes accessibles à de nombreux usages. La génération ne se limite pas au texte : code, images, audio et vidéo répondent à des architectures et contraintes différentes. Générer une image n’est pas nécessairement une opération réalisée par un LLM textuel.

La roadmap récente se lit comme une accumulation de capacités : générer, dialoguer, récupérer des informations, appeler des outils, puis organiser une exécution avec état et conditions d’arrêt. Le RAG possède des travaux fondateurs dès 2020 ; ReAct est proposé en 2022. Ces mécanismes n’ont pas attendu la diffusion commerciale du terme « agentique ».

## 2. Modèles, plateformes et hébergement — slides 7–11

Un **foundation model** est préentraîné à grande échelle et peut être adapté à plusieurs tâches. Un **LLM** est centré sur le langage ; beaucoup de LLM sont des foundation models. Certains modèles traitent plusieurs modalités. Un assistant est une application qui associe un modèle à une interface et à des composants supplémentaires.

Le panorama des usages doit être daté et sa métrique explicitée. La slide 8 reprend le classement OpenRouter au 15 novembre 2026 par **volume de tokens sur cette plateforme**, pas une part de marché mondiale ni une mesure de qualité. Les familles disponibles sur Hugging Face servent de points d’entrée pour l’exploration. Les téléchargements et les tendances du Hub ne mesurent pas non plus une qualité universelle.

Hugging Face rassemble des dépôts de modèles, données et démonstrations. La **model card** est un document à lire : tâche, langues, entraînement documenté, évaluations, licence, limites et configuration. La présence de poids accessibles ne garantit pas une licence open source ni un droit d’utilisation commerciale. Vérifier l’auteur de l’artefact, sa révision et son tokenizer.

Trois options d’hébergement répondent à des contraintes différentes : API managée, infrastructure cloud exploitée par l’équipe, machine locale. Comparer capacité, confidentialité, localisation, licence, disponibilité, débit et coût complet. Un modèle local peut fonctionner sans réseau si les poids et dépendances sont disponibles ; il consomme toujours du matériel et de l’électricité. Un GPU facilite souvent le débit mais certains modèles peuvent fonctionner sur CPU ou mémoire unifiée, avec d’autres performances.

Pour les poids seuls :

`mémoire en octets ≈ nombre de paramètres × précision en bits / 8`

| Taille | BF16, 16 bits | INT8, 8 bits | 4 bits |
|---|---:|---:|---:|
| 8 milliards | 16 Go | 8 Go | 4 Go |
| 70 milliards | 140 Go | 70 Go | 35 Go |
| 111 milliards | 222 Go | 111 Go | 55,5 Go |

Go désigne ici 10⁹ octets. Ces valeurs sont des calculs, **pas des configurations matérielles suffisantes** : ajouter métadonnées de quantification, activations, buffers et cache KV. La longueur du contexte et la concurrence augmentent les besoins. Un modèle MoE active moins de paramètres à chaque token qu’il n’en possède au total ; ses experts doivent néanmoins être stockés ou chargés. Quantifier peut affecter la qualité et ne garantit pas une accélération sur tout matériel.

## 3. Premier chat et prompt engineering — slides 12–15

Le chemin minimal est utilisateur → interface → application → modèle hébergé → réponse. L’application prépare une requête comprenant des messages et des paramètres. L’exemple emploie l’API Cohere v2, conformément à la décision du projet, avec `command-a-03-2025` comme référence pédagogique. Il ne prétend pas être le dernier modèle du fournisseur. Le détail de l’appel HTTP est disponible en approfondissement, slide 43.

Une clé est lue côté application, jamais placée dans les slides ou dans un frontend public. Une erreur de quota, d’authentification ou de réseau reste visible. Un échec live ne doit pas être remplacé silencieusement par une simulation.

Un bon prompt précise tâche, contexte, sources, format, contraintes et critères de réussite. « Résume ce document » laisse beaucoup d’ambiguïtés. « Donne le délai, le périmètre et l’exception, avec références ; écris “non précisé” si une information manque » permet une vérification. Donner un exemple de sortie peut aider. Faire évoluer le prompt sur les erreurs constatées, puis le comparer sur les mêmes questions.

Une température basse réduit parfois la variabilité ; elle n’assure pas la vérité et n’est pas réglable de la même façon pour tous les modèles. Une justification rédigée peut aussi être fausse. Demander des preuves et une explication courte vérifiable plutôt que considérer une longue chaîne de raisonnement affichée comme une garantie.

## 4. Mémoire, tokens et contexte — slides 16–20

Trois couches doivent rester distinctes :

- les paramètres contiennent des régularités apprises pendant l’entraînement ;
- le contexte est ce qui est fourni à cet appel ;
- l’application stocke éventuellement historique, résumés, préférences et documents, puis choisit quoi réinjecter.

Un appel isolé n’a pas d’historique conversationnel implicite. Une API avec sessions peut conserver cet état côté service ; ce stockage ne transforme pas la conversation en réentraînement des poids. Le cache d’inférence ne constitue pas à lui seul une mémoire métier durable. Dans le starter actuel, afficher des messages passés ne signifie pas qu’ils sont transmis au générateur.

Un token est une unité du tokenizer : mot, fragment, ponctuation ou combinaison d’octets. Avec le vocabulaire de base du tokenizer `gpt-oss-20b`, **« Bonjour, le monde ! » donne 5 tokens** : `Bonjour` / `,` / ` le` / ` monde` / ` !`. Les IDs sont `45751, 11, 505, 15807, 1073`. Les espaces font partie de certains tokens. Cette mesure ne vaut pas pour tout tokenizer. Utiliser le [tokenizer OpenAI](https://platform.openai.com/tokenizer) en notant le modèle sélectionné, ou celui du modèle réellement déployé.

Une fenêtre de contexte impose un budget. Exemple hypothétique de 32 000 tokens : 2 000 pour règles et enveloppe, 6 000 pour question et historique, 20 000 pour documents, 4 000 réservés à la sortie. Cela autorise au maximum 40 passages de 500 tokens dans cette enveloppe documentaire, si les métadonnées sont déjà comptées. Les tokens de raisonnement et plafonds de sortie dépendent de l’API. Distinguer capacité nominale du modèle, configuration du runtime et limites de l’endpoint.

Les grandes fenêtres n’assurent pas une utilisation parfaite des preuves. Les résultats historiques de *Lost in the Middle* motivent des évaluations de position et de fidélité ; ils ne donnent pas une courbe universelle pour les modèles actuels.

Le **harness** est l’environnement d’exécution : préparation du contexte, mémoire, accès aux données, outils, contrôles, traces et évaluation. Ce terme nomme un ensemble de responsabilités, pas une bibliothèque obligatoire.

## 5. RAG : deux flux et une chaîne de preuves — slides 21–28

Le schéma de la slide 21 sépare **Préparer les connaissances** (à chaque arrivée ou mise à jour documentaire) et **Répondre avec des sources** (à chaque question). Le premier flux écrit chunks, vecteurs et métadonnées dans l’index commun. Le second l’interroge avec des filtres de droits, sélectionne des passages puis les fournit avec la question au modèle. Les flèches distinguent écriture, requête et retour de preuves.

L’ingestion et la question-réponse ont des temporalités différentes. À l’ingestion : extraire, découper, identifier, encoder et indexer. À la question : appliquer les droits, rechercher, sélectionner, borner le contexte, générer et restituer les sources. Un RAG ne réentraîne pas les poids et n’impose pas nécessairement un moteur vectoriel : il peut utiliser de la recherche lexicale, vectorielle ou hybride.

L’extraction dépend du support. Un PDF texte peut être parsé ; un scan nécessite une reconnaissance optique des caractères (**OCR**). Tesseract, EasyOCR et RapidOCR sont des exemples de moteurs. Docling propose une chaîne de conversion documentaire et des options OCR. Un modèle de vision peut aider sur une page ou un tableau ; il peut aussi omettre ou inventer une valeur. La multimodalité ne rend pas automatiquement tout fichier lisible sans prétraitement.

Conserver la structure, les conditions, les unités, la page et la provenance. Le premier TP reste volontairement sur TXT/Markdown : PDF, OCR et tableaux sont des extensions théoriques. Un chunk est relié à un document, une version, une position et des règles d’accès. Une réindexation doit retirer les informations devenues obsolètes et éviter les doublons.

Un **embedding** encode une entrée en un vecteur. Les représentations compatibles permettent de comparer une question et des passages. La proximité reflète des similarités apprises, pas la vérité ou l’accès autorisé. La visualisation 2D de la slide 24 est une construction fictive, pas une projection mesurée. Les dimensions d’un embedding réel n’ont généralement pas des significations métier directement lisibles.

Ces représentations servent aussi à recommander, regrouper, chercher des images ou produire des candidats doublons. Les modalités doivent être alignées par un modèle adapté. Une classification ou une analyse de sentiments demande une méthode et une évaluation supplémentaires.

Dans l’exemple, l’ancienne procédure parle de 60 minutes et la nouvelle de 30. Un filtre de version écarte le passage obsolète. La réponse doit citer la bonne source. Une citation existante ne garantit pas que l’affirmation est soutenue par le passage : contrôler **validité de la citation** et **fidélité** séparément. Sans preuve suffisante, expliquer le manque ou s’abstenir. Mesurer aussi récupération, latence et comportement hors corpus.

## 6. Au-delà de la recherche — slides 29–34

Le RAG documentaire répond à la partie « délai ». Pour l’état actuel du ticket, un outil métier doit être interrogé. Un agent peut sélectionner des recherches et outils dans une boucle ; il peut aussi multiplier coûts et erreurs. Un workflow fixe suffit si les étapes sont connues.

L’**Open Knowledge Format**, vérifié en v0.2, représente des connaissances en fichiers Markdown avec métadonnées YAML et liens. Il facilite organisation et portabilité ; un agent peut les parcourir et un moteur peut les indexer. C’est une proposition émergente qui complète le RAG. Elle ne supprime ni contexte limité, ni besoin de curation, ni contrôle d’accès ; aucun gain universel n’est affirmé ici.

Les slides 30–31 montrent concrètement cette utilisation. L’hôte fournit des outils de lecture et un point d’entrée. Dans l’exemple, l’agent lit `index.md`, ouvre `playbooks/p1.md`, suit son lien vers `references/delais.md`, puis sélectionne les extraits utiles pour le contexte du modèle. Il peut répondre avec la référence du délai. Pour connaître l’état courant du ticket, il doit encore appeler le service métier. Les fichiers OKF ne s’exécutent pas tout seuls et ne sont pas tous chargés automatiquement en mémoire ; chaque accès reste soumis aux droits et au budget.

LangChain facilite intégrations et agents ; LangGraph rend état et transitions explicites ; LlamaIndex outille les applications connectées aux données ; Google ADK fournit des composants d’agents, outils, sessions et exécution. Leurs périmètres se recoupent. Ils ne fournissent pas automatiquement la bonne architecture ou une sélection optimale du modèle.

Un **tool** est une opération à contrat, **MCP** standardise l’accès à des capacités, un **skill** décrit une procédure réutilisable. Le cours 2 développe ces distinctions, leurs contrôles et la boucle bornée.

## 7. Travail, ressources, règles — slides 35–40

L’étude Anthropic du 5 mars 2026 distingue capacité théorique et exposition observée à partir d’usages de Claude. Pour « Computer & Math », elle publie 94 % de capacité théorique et 33 % de couverture observée des tâches. Le périmètre et la méthode sont spécifiques ; ces valeurs ne prédisent pas une proportion d’emplois supprimés. Discuter transformation des tâches, contrôle, formation des juniors et responsabilités.

La slide 36 présente des métiers dont les missions se renforcent avec l’IA. Le **FDE (Forward Deployed Engineer)** construit et déploie avec l’équipe cliente, de la découverte du besoin aux évaluations et à l’adoption. Le **FDA (Forward Deployed Architect)** relie contexte métier, architecture et mise en œuvre, avec des composants réutilisables. Les rôles se recouvrent selon l’organisation ; le FDA peut aussi coder. Des spécialistes Applied AI, data/knowledge et métier/produit complètent l’équipe. Ces intitulés ne prouvent ni une création nette d’emplois ni la disparition des métiers existants.

L’AIE indique environ 485 TWh pour les centres de données mondiaux en 2025 et projette environ 950 TWh en 2030 dans sa mise à jour de 2026. Le périmètre comprend tous les centres de données, pas uniquement l’IA. À l’échelle d’un service, considérer entraînement et inférence, fabrication, eau, mix électrique, localisation, utilisation du matériel et effets de volume. Choisir puis mesurer le système le plus sobre qui atteint la qualité attendue.

L’AI Act qualifie des usages et des rôles. Les obligations d’un fournisseur de modèle à usage général ne sont pas celles de tout déployeur. Les repères présentés incluent les pratiques interdites et la maîtrise de l’IA en 2025, des obligations GPAI, la transparence en août 2026 et les échéances de haut risque révisées en 2026. Le calendrier de la Commission indique le 2 décembre 2027 pour l’annexe III et le 2 août 2028 pour les systèmes intégrés aux produits réglementés. Ce sont des repères sélectifs ; vérifier dispositions et transitions applicables. Le RGPD, la confidentialité et les droits sur les contenus restent à examiner.

Enfin, un document peut porter une prompt injection. Ses instructions ne doivent pas acquérir les privilèges des règles de l’application. Les filtres de droits, validations d’arguments et politiques d’action se mettent dans le code et les services, pas uniquement dans un prompt.

## Pour le projet

Les lots 1–2 remplacent la simulation par un fournisseur explicite, puis ajoutent un petit RAG avec sources. La vérification de l’abstention et de la réindexation peut finir en S3. Les comportements cibles restent ceux de [la spécification des flux IA](../../../../course-authoring/docs/specs/01_AI_FLOWS.md).

La [carte finale](slides.html#slide-48) relie interface, instructions, mémoire, budget de contexte, orchestration, modèle, tools, MCP, connaissances RAG et OKF, skills et validation. Le bandeau inférieur rappelle les choix d’hébergement et les contraintes humaines, matérielles et réglementaires.

Retrouver les [sources et leurs limites](sources.md), la [synthèse](synthese.md) et le [quiz sans correction](quiz.md).
