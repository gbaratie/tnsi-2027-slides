# RSE — références et périmètres

Sources consultées le **12 novembre 2026**. Les données historiques gardent leur période ; les éléments réglementaires devront être revérifiés avant projection. Les captures de l’auteur ont guidé la sélection des sujets ; les références ci-dessous étayent les faits affichés.

## S01 — Enjeux sociaux

[Insee — Compétences numériques de la population, édition 2025](https://www.insee.fr/fr/statistiques/8616801) : enquête TIC ménages **2023**, France hors Mayotte, personnes de 15 ans ou plus. **15,7 %** sont en situation d’illectronisme. Cet indicateur ne mesure ni le handicap ni la conformité d’un service web à un référentiel d’accessibilité.

## S02 — Limites planétaires

[Planetary Health Check 2026, 21 septembre 2026](https://www.planetaryhealthcheck.org/2026-planetary-health-check-launched-at-new-york-climate-week/) : évaluation annuelle produite par le laboratoire Planetary Boundaries Science Lab du PIK. **Sept des neuf frontières** sont transgressées ; l’acidification des océans est passée au-delà de la frontière en 2025. La figure du deck est une représentation catégorielle pédagogique, sans échelle de dépassement inventée.

Le cadre des limites planétaires est distinct des rapports du GIEC. Un dépassement exprime un risque accru pour la stabilité du système terrestre, sans être une date de bascule garantie ni un quota automatiquement attribué à une entreprise. Ozone et aérosols sont ici décrits au niveau global ; les situations régionales peuvent différer.

## S03 — GIEC : leviers documentés

- [AR6 WGIII, Summary for Policymakers, 2022](https://www.ipcc.ch/report/ar6/wg3/chapter/summary-for-policymakers/) : section B.4.1, baisses des coûts unitaires entre **2010 et 2019** : solaire **85 %**, éolien **55 %**, batteries lithium-ion **85 %**.
- [AR6, rapport de synthèse 2023, texte long](https://www.ipcc.ch/report/ar6/syr/longer-report/) : reprise des mêmes évolutions et de leur contexte.
- AR6 WGIII **C.12** : des options d’atténuation à **100 USD/tCO₂e ou moins** ont un potentiel de réduction au moins égal à la moitié des émissions mondiales de 2019 à l’horizon 2030, avec confiance élevée. Il s’agit d’un potentiel conditionnel, pas d’une prévision d’atteinte de cette réduction.
- [Figure SPM.7 et données officielles](https://ipcc-data.climate.columbia.edu/content/ar6-wgiii-spm7) : coûts et potentiels varient selon les régions, technologies et hypothèses ; les options ne s’additionnent pas simplement.

La figure de coûts est un tracé original des trois variations publiées, pas une nouvelle série temporelle ou une mesure des émissions. Le rapport WGIII est daté de 2022 ; la synthèse de l’AR6 est de 2023. Le [rapport complet donné par l’auteur](https://www.ipcc.ch/report/ar6/wg3/downloads/report/IPCC_AR6_WGIII_FullReport.pdf) reste une référence pour approfondir.

## S04 — Cycle de vie et écoconception

[Arcep — Référentiel général d’écoconception des services numériques, 17 mai 2024](https://www.arcep.fr/mes-demarches-et-services/entreprises/fiches-pratiques/referentiel-general-ecoconception-services-numeriques.html) : utilité, durée de vie des équipements, ressources, transparence et contrôle des choix. Les critères 1.1 et 1.5 étayent la distinction entre service utile, cycle de vie, indicateurs relatifs et absolus.

Le score d’avancement du RGESN évalue une démarche de mise en œuvre ; il n’est pas une mesure d’impact environnemental. Mutualisation, cache, choix matériel ou cloud doivent être examinés avec leurs conditions, leurs volumes et leurs effets amont.

## S05 — Consensus et consommation électrique

[Ethereum — The Merge](https://ethereum.org/roadmap/merge/) : transition PoW → PoS le **15 septembre 2022**, baisse estimée d’environ **99,95 %** de la consommation électrique du réseau. Le mécanisme PoW repose sur une compétition calculatoire ; le PoS utilise un mécanisme différent de sélection et de validation avec enjeu immobilisé.

Le chiffre est une estimation à l’échelle du même réseau, pas une énergie fixe par transaction, une analyse complète de cycle de vie ou la preuve que tous les usages de blockchain sont utiles. Les compromis de sécurité et de gouvernance restent à analyser.

## S06 — Énergie des modèles : un exemple de benchmark

- [AI Energy Score — méthodologie](https://huggingface.github.io/AIEnergyScore/) : mesures par tâche sur matériel H100, centrées sur l’énergie GPU. Les performances doivent être examinées en parallèle.
- [Leaderboard et données originales](https://huggingface.co/spaces/AIEnergyScore/Leaderboard) ; [CSV génération de texte](https://huggingface.co/spaces/AIEnergyScore/Leaderboard/raw/main/data/energy/text_generation.csv) ; [code de présentation des unités](https://huggingface.co/spaces/AIEnergyScore/Leaderboard/blob/main/app.py).
- [Présentation de la mise à jour du 4 décembre 2025](https://huggingface.co/blog/sasha/ai-energy-score-v2) : protocole, cohortes et effet des modes de raisonnement.

Sélection du deck : tâche **génération de texte**, cohorte **décembre 2025**, classe **A**. Pour 1 000 requêtes du benchmark : **SmolLM3-3B : 18,35 Wh ; Mistral-Nemo-Instruct-2407 : 23,19 Wh ; Gemma-3-4b-pt : 34,39 Wh**. Le code du leaderboard multiplie `total_gpu_energy` par 1 000 pour afficher les Wh. La copie CSV et les lignes sélectionnées accompagnent les assets.

Le protocole permet une comparaison de son énergie GPU ; il ne garantit pas une qualité métier équivalente et ne mesure pas toute l’infrastructure ni le cycle de vie. Ces valeurs ne sont pas des prix ni des consommations garanties en production. Le nombre de tokens, les erreurs, le matériel, le batching et les modes de génération comptent.

## S07 — Eau et périmètres des déclarations IA

- [Google, mesure d’inférence en production, août 2025](https://cloud.google.com/blog/products/infrastructure/measuring-the-environmental-impact-of-ai-inference) ; [article technique des auteurs](https://arxiv.org/abs/2508.15734) : données **mai 2025**, médiane d’un prompt texte Gemini Apps, **0,24 Wh** et **0,26 mL** d’eau consommée sur site. La médiane n’est pas une moyenne universelle de toutes les demandes.
- [Mistral AI, 22 juillet 2025](https://mistral.ai/news/our-contribution-to-a-global-environmental-standard-for-ai/) : impact marginal d’inférence du Chat pour une **réponse de 400 tokens**, hors terminaux des utilisateurs, **45 mL** d’eau, **1,14 gCO₂e**. L’analyse prend aussi en compte des effets amont. L’énergie par requête n’est pas publiée dans cette déclaration.

Les unités fonctionnelles et frontières diffèrent. Aucun ratio ni classement des deux offres n’est calculé dans le deck. Distinguer prélèvement, consommation, eau directe et indirecte, volume physique et indicateur de rareté. Le stress dépend aussi du bassin et de la saison ; il ne découle pas du seul volume par requête. Les trois indicateurs de Mistral ne se réduisent pas à une seule mesure d’électricité.

## S08 — Calcul pédagogique de volume

Exemple **fictif**, sans nom de fournisseur : 100 000 requêtes/mois à 0,8 Wh = 80 kWh opérationnels ; après optimisation, 0,2 Wh par requête. Le total dépend du nouveau volume. Les nombres servent à expliquer unités et multiplication ; ils ne décrivent aucun service réel et ne constituent pas une ACV.

## S09 — CSRD, ESRS et double matérialité

- [Conseil UE, adoption finale du 24 février 2026](https://www.consilium.europa.eu/en/press/press-releases/2026/02/24/council-signs-off-simplification-of-sustainability-reporting-and-due-diligence-requirements-to-boost-eu-competitiveness/) ; [directive (UE) 2026/470](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32026L0470) : modification du périmètre général UE de la CSRD, notamment **plus de 1 000 salariés et plus de 450 M€ de chiffre d’affaires net**. Règles de groupe, exceptions, exercices et transposition nationale doivent être vérifiés.
- [EFRAG IG 1 — Materiality Assessment](https://knowledgehub.efrag.org/eng/interactive/ig/ig1/09-2025/52-faqs-on-financial-materiality) : matérialité des impacts et matérialité financière. Un sujet peut être matériel selon l’une, l’autre ou les deux perspectives ; ce n’est pas l’obligation de ne retenir que leur intersection.

La CSRD est une directive, pas le nom d’un règlement directement uniforme. Les ESRS structurent l’information ; le reporting n’établit pas, à lui seul, une performance durable. Un fournisseur hors champ peut recevoir des demandes de données sans devenir directement soumis aux obligations de son client. Les rangs fournisseurs et les scopes d’émissions sont distincts. L’ancien calendrier des captures auteur n’est pas repris.

## S10 — AI Act et calendrier actualisé

- [Commission européenne — cadre AI Act et calendrier](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai).
- [Commission européenne — entrée en vigueur de l’AI Omnibus, 27 juillet 2026](https://digital-strategy.ec.europa.eu/en/news/ai-omnibus-enters-force) : haut risque **annexe III au 2 décembre 2027** ; systèmes à haut risque intégrés aux produits **annexe I au 2 août 2028**. Les premières interdictions s’appliquent depuis 2025 ; les autres dispositions et transitions dépendent du cas.

Le rôle de l’organisation et l’usage exact déterminent les obligations. Le seul nom d’un secteur ne suffit pas. La transparence, les droits et la sécurité des personnes ne se confondent pas avec une certification écologique du système. Cette capsule est un repère pédagogique daté, pas une qualification juridique d’entreprise.

## S11 — Acteurs, responsabilités et métiers

[Apec — Responsable RSE](https://www.apec.fr/tous-nos-metiers/ressources-humaines/responsable-rse.html) : diagnostic, besoins des parties prenantes, indicateurs, projets, coordination et reporting. Le RGESN décrit aussi les métiers concernés et les contrôles. La répartition présentée est pédagogique : les rôles peuvent être partagés, regroupés ou externalisés.

Institutions citées par fonction : GIEC, PIK/SRC et Insee pour la connaissance ; ADEME, Arcep et RGESN pour l’évaluation et la conception ; UE et EFRAG pour le cadre réglementaire et les ESRS. Aucun classement commercial n’est proposé.

## S12 — Scopes et chaîne de valeur

[GHG Protocol — Standards](https://ghgprotocol.org/standards), Corporate Standard et Corporate Value Chain (Scope 3) Standard : les scopes classent les émissions selon leur relation avec l’organisation. Les rangs fournisseurs décrivent une position dans la chaîne d’approvisionnement ; ils ne correspondent pas aux scopes 1, 2 et 3.
