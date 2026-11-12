# Sources du deck quantique

**Rôle :** justifier les concepts et les exemples du [deck](slides.html).

**Vérification :** 12 novembre 2026. Les dates des résultats restent affichées ; un exemple historique n’est pas présenté comme une actualité. Les liens pointent vers des ressources primaires.

## Bases de l’information quantique — slides 2 à 6 et annexe 19

- [IBM Quantum Learning — Quantum information](https://quantum.cloud.ibm.com/learning/en/courses/basics-of-quantum-information/single-systems/quantum-information) : amplitudes complexes, normalisation, mesure et différence entre état quantique et distribution classique.
- [IBM Quantum Learning — Bits, gates, and circuits](https://quantum.cloud.ibm.com/learning/en/courses/utility-scale-quantum-computing/bits-gates-and-circuits) : portes, circuits, superposition et intrication.
- [IBM Quantum Learning — Entanglement in action](https://quantum.cloud.ibm.com/learning/en/courses/basics-of-quantum-information/entanglement-in-action/introduction) : état partagé et ressources de communication. Des résultats corrélés dans une seule base ne suffisent pas à démontrer l’intrication ; celle-ci ne permet pas l’envoi instantané d’un message.
- [IBM Quantum Learning — Grover’s algorithm](https://quantum.cloud.ibm.com/learning/en/courses/fundamentals-of-quantum-algorithms/grover-algorithm/introduction) : amélioration quadratique du nombre de requêtes dans le modèle de recherche non structurée. Le coût de l’oracle et du chargement des données compte dans une application réelle.

La démonstration `H → P(φ) → H` est un calcul analytique d’un circuit idéal à un qubit. Les probabilités affichées et l’échantillonnage simulé doivent être distingués.

## Correction d’erreurs — slides 7 et 8 et annexe 20

- Google Quantum AI et collaborateurs, [« Quantum error correction below the surface code threshold »](https://doi.org/10.1038/s41586-024-08449-y), publication en ligne le **9 décembre 2024**, *Nature* 638, 920–926 (**2025**). [Texte intégral déposé dans PubMed Central](https://pmc.ncbi.nlm.nih.gov/articles/PMC11864966/).
- [Explication par les chercheurs de Google](https://research.google/blog/making-quantum-error-correction-work/), **9 décembre 2024**.

L’expérience porte sur une mémoire logique sous le seuil de correction. Elle illustre une réduction des erreurs lorsque la protection augmente dans les conditions de l’expérience. Elle ne démontre pas, à elle seule, un ordinateur universel tolérant aux fautes utile à une entreprise. Aucun ratio universel « qubits physiques par qubit logique » n’est déduit.

## Chimie et matériaux — slide 10 et annexe 16

J. Robledo-Moreno et al., [« Chemistry Beyond the Scale of Exact Diagonalization on a Quantum-Centric Supercomputer »](https://doi.org/10.1126/sciadv.adu9991), *Science Advances* 11(25), eadu9991 (**2025**). [Manuscrit des auteurs, arXiv:2405.05068](https://arxiv.org/abs/2405.05068), première version **2024**, révision consultée **13 juillet 2025**.

L’équipe combine le processeur Heron et le supercalculateur Fugaku pour étudier N₂ et des agrégats [2Fe–2S] et [4Fe–4S], avec des circuits allant jusqu’à **77 qubits**. Le résultat dépasse les tailles accessibles à la diagonalisation exacte utilisée comme référence. Cette comparaison n’établit pas un avantage économique face à toutes les méthodes classiques approximatives ni la découverte d’un médicament.

## Optimisation et mobilité — slide 10 et annexe 17

[Airbus et BMW Group — résultats du Quantum Computing Challenge](https://www.airbus.com/en/newsroom/press-releases/2024-12-quantum-leaps-winners-of-airbus-and-bmw-groups-quantum-computing), **10 décembre 2024**.

Le communiqué identifie notamment un cas de logistique porté par **4colors Research**, ainsi que des travaux en simulation, résolution d’équations et apprentissage automatique. Il s’agit d’une source industrielle décrivant un challenge et des pistes d’application. Elle ne fournit pas un benchmark indépendant établissant un gain économique généralisable ; certains travaux évoqués sont quantiques ou inspirés du quantique. Le deck présente donc cet exemple comme un pilote à évaluer.

## Cryptographie — slides 13 et 14 et annexe 21

- [NIST — publication des trois premiers standards PQC](https://www.nist.gov/news-events/news/2024/08/nist-releases-first-3-finalized-post-quantum-encryption-standards), **13 août 2024** : FIPS 203 (**ML-KEM**, établissement de clé), FIPS 204 (**ML-DSA**, signature), FIPS 205 (**SLH-DSA**, signature). Cette première série n’est pas présentée comme la liste exhaustive des travaux de normalisation.
- [NIST — What Is Post-Quantum Cryptography?](https://www.nist.gov/cybersecurity-and-privacy/what-post-quantum-cryptography) : algorithmes sur machines classiques conçus pour résister aux attaques quantiques connues ; préparation de la transition.
- [ANSSI et partenaires — Position Paper on Quantum Key Distribution](https://cyber.gouv.fr/nous-connaitre/publications/publications-internationales/position-paper-on-quantum-key-distribution/) : portée et limites de la QKD, priorité donnée à la PQC pour la migration des organisations.

L’algorithme de Shor menace la factorisation et le logarithme discret avec une machine suffisamment grande et fiable ; aucune date de rupture RSA/ECC n’est avancée. Le risque « collecter maintenant, déchiffrer plus tard » concerne notamment la durée de confidentialité et les mécanismes d’établissement des clés. ML-KEM n’est pas un algorithme de chiffrement des données applicatives. La migration dépend des protocoles, des produits, de l’interopérabilité et des recommandations de sécurité applicables.

## Capteurs — slide 10 et annexe 18

B. Stray et al., [« Quantum sensing for gravity cartography »](https://doi.org/10.1038/s41586-021-04315-3), *Nature* 602, 590–594 (**2022**). [Notice et résumé des auteurs, University of Birmingham](https://research.birmingham.ac.uk/en/publications/quantum-sensing-for-gravity-cartography/).

Un gradiomètre quantique détecte un tunnel dans une expérience extérieure. Le « 2 mètres » du résumé décrit le tunnel ; il ne doit pas être confondu avec une profondeur universelle de détection. Les perspectives concernent la cartographie du sous-sol et les infrastructures. Cet exemple démontre un capteur en conditions de terrain, sans établir une adoption généralisée ou un remplacement universel des méthodes de prospection.

## Lecture de la maturité — slides 9 à 11 et annexe 20

[DARPA — Quantum Benchmarking Initiative](https://www.darpa.mil/research/programs/quantum-benchmarking-initiative), page consultée le **12 novembre 2026**.

Le programme évalue la possibilité d’un calcul dont la valeur dépasse le coût. Son horizon d’évaluation n’est pas une date de disponibilité garantie. Les niveaux de maturité sont une lecture pédagogique des références ci-dessus.

## Comparaison classique / quantique et propriétés — slides 2 et 3

- [Intel — The Transistor, Explained](https://www.intel.com/content/www/us/en/newsroom/tech101/the-transistor-explained.html) : rôle du transistor comme commutateur électronique et organisation de l’information binaire.
- [IBM — Limitations on quantum information](https://quantum.cloud.ibm.com/learning/en/courses/basics-of-quantum-information/quantum-circuits/limitations-on-quantum-information) : impossibilité de cloner parfaitement un état arbitraire inconnu. Cela n’interdit pas de copier des états particuliers connus, ni de préparer plusieurs fois un même circuit.

Le transistor est un composant physique ; le bit et le qubit sont des unités d’information. Le deck ne suppose ni un transistor par bit ni un remplacement composant pour composant. La cohérence, la superposition et la mesure sont expliquées avec les références IBM des bases et de la correction d’erreurs.

## Repères historiques — slide 8

- **1982** : R. Feynman, [« Simulating physics with computers »](https://authors.library.caltech.edu/records/a1kgk-xyk45), *International Journal of Theoretical Physics* 21, 467–488 ; [DOI](https://doi.org/10.1007/BF02650179). Le deck date l’article de 1982, sans le confondre avec la conférence de 1981.
- **1994** : P. Shor, [« Algorithms for quantum computation: discrete logarithms and factoring »](https://doi.org/10.1109/SFCS.1994.365700), FOCS 1994 ; [notice du rapport DIMACS de l’auteur](https://archive.dimacs.rutgers.edu/TechnicalReports/abstracts/1994.sav/94-37.html).
- **4 mai 2016** : [IBM ouvre l’accès à son processeur via le cloud](https://uk.newsroom.ibm.com/2016-May-04-IBM-Makes-Quantum-Computing-Available-on-IBM-Cloud-to-Accelerate-Innovation). Il s’agit de l’annonce originale du service.
- **2024 / 2025** : mémoire logique Willow, publication en ligne en décembre 2024 et volume de *Nature* en 2025 ; voir la référence de correction d’erreurs.
- **19 août 2026** : [IBM annonce l’interconnexion de deux modules cryogéniques](https://newsroom.ibm.com/2026-08-19-ibm-connects-its-first-modular-cryogenic-systems-in-milestone-toward-fault-tolerant-quantum-computing/). Ce repère d’ingénierie est attribué au constructeur ; ce n’est pas l’annonce d’un calculateur tolérant aux fautes déjà achevé.

## Roadmaps futures — slide 9

| Horizon | Source primaire | Nature et portée du jalon |
|---|---|---|
| 2027 | [DGE, 26 mai 2026](https://www.entreprises.gouv.fr/la-dge/actualites/france-2030-la-france-accelere-sa-strategie-quantique-pour-renforcer-sa) | Installation annoncée de Kity, d’Alice & Bob, au TGCC. L’installation d’un système n’établit pas un avantage industriel. |
| 2029 | [IBM, mise à jour du 11 novembre 2026](https://www.ibm.com/quantum/blog/path-to-ibm-quantum-starling) ; [roadmap](https://www.ibm.com/roadmaps/quantum/) | Objectif Starling : 200 qubits logiques et 100 millions d’opérations. Engagement de roadmap d’un constructeur, pas un résultat acquis. |
| 2032 | [DGE, 26 mai 2026](https://www.entreprises.gouv.fr/la-dge/actualites/france-2030-la-france-accelere-sa-strategie-quantique-pour-renforcer-sa) | PROQCIMA : objectif relevé de 128 à **1 024 qubits logiques**. Les documents initiaux de 2024 parlant de 128 sont dépassés sur ce point. |
| 2033 | [DARPA — QBI](https://www.darpa.mil/research/programs/quantum-benchmarking-initiative) | Horizon d’évaluation de la possibilité d’un calcul industriel utile dont la valeur dépasse le coût. Le programme n’assure pas que les candidats réussiront. |

Ces jalons diffèrent par leur objet : installation, capacités cibles ou évaluation. Aucun n’est présenté comme une date garantie de disponibilité générale ou de rupture cryptographique. Les chiffres de qubits physiques et logiques ne sont pas mélangés.

## Acteurs et focus France — slide 11

- [DARPA — participants QBI et technologies](https://www.darpa.mil/research/programs/quantum-benchmarking-initiative) : notamment IBM et Google (supraconducteurs), IonQ et Quantinuum (ions), QuEra et Atom Computing (atomes neutres), PsiQuantum et Xanadu (photonique). L’état de participation au programme n’est pas utilisé comme un classement.
- [AWS — matériels accessibles dans Braket](https://docs.aws.amazon.com/braket/latest/developerguide/braket-devices.html) et [présentation des machines](https://aws.amazon.com/braket/quantum-computers/) : notamment IQM et Rigetti pour les supraconducteurs.
- [D-Wave — What is Quantum Annealing?](https://docs.dwavequantum.com/en/latest/quantum_research/quantum_annealing_intro.html) : recuit pour optimisation et échantillonnage, modèle distinct des circuits à portes.
- [DGE — écosystème français et HQI](https://www.entreprises.gouv.fr/la-dge/actualites/france-2030-la-france-accelere-sa-strategie-quantique-pour-renforcer-sa) : cinq entreprises de la première phase de PROQCIMA et machines Ruby et Lucy au TGCC.
- [Pasqal — documentation QPU](https://docs.pasqal.com/qpu-emulators/qpus/) : atomes neutres ; [Quandela / Perceval](https://github.com/Quandela/Perceval) : photonique ; [Alice & Bob](https://alice-bob.com/) : qubits de chat.
- [C12 — notice du Conseil européen de l’innovation](https://eic.ec.europa.eu/eic-fund/eic-fund-portfolio/c12-quantum-electronics_en) : nanotubes de carbone ; [Quobly — annonce technologique](https://www.quobly.io/press-releases/quobly-demonstrates-key-quantum-operations-on-single-industrial-silicon-chip-advancing-toward-large-scale-quantum-computing/) : spins dans le silicium.

Le panorama est sélectif et associe des acteurs à leur approche, sans classement de performance ou de part de marché. Les plateformes AWS et Microsoft Azure sont présentées comme des accès à des matériels de fournisseurs.

## Accès cloud — slide 12

| Plateforme | Source primaire | Ce que le deck propose |
|---|---|---|
| IBM Quantum | [Composer](https://quantum.cloud.ibm.com/docs/en/guides/composer) ; [plans](https://quantum.cloud.ibm.com/docs/en/ibm-quantum-platform/plans-overview) | Construction graphique, visualisation et exécution sur QPU avec compte. Le plan Open annonce l’équivalent de jusqu’à 10 min QPU par fenêtre glissante de 28 jours, en unités de ressource dans la documentation de novembre 2026. Les promotions temporaires ne sont pas présentées comme le quota standard. |
| Amazon Braket | [Matériels et régions](https://docs.aws.amazon.com/braket/latest/developerguide/braket-devices.html) ; [tarification](https://aws.amazon.com/braket/pricing/) | Matériels de plusieurs fournisseurs et simulateurs ; compte et facturation AWS selon les ressources. |
| Azure Quantum | [Fournisseurs](https://learn.microsoft.com/en-us/azure/quantum/qc-target-list) ; [tarification](https://learn.microsoft.com/en-us/azure/quantum/pricing) | Espace de travail, fournisseur et offre d’accès ; la disponibilité dépend du compte et de la région. |
| Quandela Cloud | [Portail](https://cloud.quandela.com/) ; [Perceval, dépôt officiel](https://github.com/Quandela/Perceval) | Circuits photoniques, simulateurs et QPU selon l’accès au compte. Le portail est rendu en JavaScript ; les capacités sont aussi documentées par le dépôt officiel. |
| Pasqal Cloud | [Documentation](https://docs.pasqal.com/cloud/) ; [mise en place](https://docs.pasqal.com/cloud/set-up/) | Envoi de calculs aux QPU à atomes neutres ou aux émulateurs selon l’offre. |

Les liens constituent un appel à l’action après le cours, pas une exécution automatisée ni la création de ressources. Les tarifs, quotas, machines, accès et files d’attente doivent être revérifiés avant l’atelier. Pour l’état de Bell, les résultats idéaux et les fréquences matérielles sont distingués ; une corrélation dans la seule base 0/1 ne prouve pas l’intrication.

## Quantum Safe et plan d’action — slides 13 et 14

- [ANSSI — FAQ sur la PQC](https://cyber.gouv.fr/enjeux-technologiques/cryptographie-post-quantique/faq-pqc/) : inventaire des produits, des usages et des algorithmes, durée de protection attendue et préparation de la migration.
- [ANSSI — analyse de risque chiffrement et cryptographie, 27 mai 2026](https://cyber.gouv.fr/nous-connaitre/publications/analyse-de-risque-sectorielle-et-technique/analyse-de-risque-chiffrement-et-cryptographie/) : sensibilisation et transition vers des solutions résistantes aux attaques quantiques.
- [Commission européenne — feuille de route PQC](https://digital-strategy.ec.europa.eu/en/policies/post-quantum-cryptography) : feuille de route adoptée en juin 2025, démarrage recommandé des transitions des États membres avant fin 2026 et protection des usages à haut risque avant fin 2030. Il ne s’agit pas d’une obligation générale identique pour toutes les organisations.

Quantum Safe est présenté comme une démarche de résistance du système, incluant confidentialité et authenticité. La PQC s’exécute sur des machines classiques ; les protocoles, logiciels, certificats, signatures de mises à jour et équipements font partie du périmètre. Les standards NIST de 2024 restent des repères, sans être une liste exhaustive des travaux. La sélection de produits et d’hybridations doit suivre les recommandations applicables et des essais d’interopérabilité.
