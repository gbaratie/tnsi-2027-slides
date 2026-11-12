# Blockchain — sources, dates et périmètres

Consultation et préparation : **12 novembre 2026**. Les captures auteur guident la progression ; leurs simplifications sont précisées dans le cours. La conclusion reprend l’illustration du deck Intro.

## Origine et mécanismes

- [Bitcoin, livre blanc de Satoshi Nakamoto, 2008](https://bitcoin.org/bitcoin.pdf) : paiement pair à pair, double dépense, ordre des transactions et hypothèses du réseau. Repère historique, sans assimiler toute blockchain au protocole Bitcoin.
- [Guide développeur Bitcoin : chaîne de blocs](https://developer.bitcoin.org/devguide/block_chain.html) : blocs, empreintes, validation indépendante et choix de chaîne. La règle du travail cumulé dépasse une simple comparaison du nombre de blocs.
- [Ethereum : nœuds et clients](https://ethereum.org/developers/docs/nodes-and-clients/) : fonctions de vérification, historique et clients légers. Modes de synchronisation et conservation dépendent du client ; un nœud complet ne conserve pas nécessairement tous les états historiques.
- [Ethereum : wallets](https://ethereum.org/wallets/) : outil d’accès aux comptes et clés ; distinguer wallet, adresse, compte et actif. La garde par un prestataire ajoute une relation de confiance.
- [Ethereum : smart contracts](https://ethereum.org/developers/docs/smart-contracts/) : programmes et état ; limites concernant l’accès aux événements extérieurs. Un oracle est une source supplémentaire, pas une garantie de vérité.

La maquette du cours emploie un vrai calcul SHA-256 local sur des blocs fictifs, sans format Bitcoin, minage, validation distante ni réseau. Recalculer les empreintes d’une copie ne lui donne pas l’acceptation des autres participants.

## Consensus et familles de réseaux

- [Ethereum : mécanismes de consensus](https://ethereum.org/developers/docs/consensus-mechanisms/) : PoW/PoS ne sont pas, seuls, des protocoles complets ; sélection du producteur, résistance aux identités multiples, choix de branche et finalité sont à distinguer.
- [Antelope : contrats système](https://docs.antelope.io/reference-contracts/latest/about_system_contracts/) : sélection d’un ensemble de producteurs par délégation, exemple documenté de DPoS. Toute délégation de staking n’implique pas le même mécanisme électif.
- [Besu : QBFT](https://docs.besu-eth.org/private-networks/how-to/configure/consensus/qbft) : validateurs autorisés, signatures de quorum et hypothèses de fautes. L’exemple de quatre validateurs / un fautif / trois signatures est une illustration simplifiée, sous les hypothèses du protocole.
- [Hyperledger Fabric : introduction](https://hyperledger-fabric.readthedocs.io/en/latest/whatis.html) : plateforme permissionnée, identités, politiques et séparation de fonctions. Fabric est un logiciel ; Besu est un client EVM utilisé sur réseaux publics ou privés, pas un jeton concurrent de BTC.
- [Solana Foundation : Alpenglow](https://solana.com/upgrades/alpenglow), mise à jour octobre 2026 : activation de Votor sur mainnet le **21 octobre 2026**, epoch 1064 ; Rotor reste une phase ultérieure. Le tableau du cours est actualisé et ne présente pas l’ancien TowerBFT/PoH comme le consensus actuel. Les cibles de performance du projet ne sont pas reprises comme benchmark entre réseaux.

Public/privé et permissionné/non permissionné décrivent plusieurs dimensions : consultation, soumission, production/validation, gouvernance et confidentialité. Elles ne sont pas réduites à une unique opposition technique.

## Échelle, interopérabilité, actifs et Web3

- [Ethereum : passage à l’échelle](https://ethereum.org/developers/docs/scaling/) et [réseaux de couche 2](https://ethereum.org/layer-2/) : rollups et ancrage sur L1 ; disponibilité des données, preuves et mécanismes de sortie doivent être examinés.
- [Ethereum : ponts](https://ethereum.org/bridges/) : familles d’interopérabilité et risques additionnels. Verrouiller/représenter est un exemple de conception, pas la description de tous les ponts.
- [ERC-721, standard final, créé le 24 janvier 2018](https://eips.ethereum.org/EIPS/eip-721) : identifiant unique dans un contrat et métadonnées optionnelles. Un NFT n’établit pas seul une licence d’exploitation ou la propriété juridique d’un bien.
- [Ethereum : Web3](https://ethereum.org/web3/) : vision et architecture d’applications liées aux blockchains. Les promesses de propriété et de désintermédiation sont examinées avec les dépendances concrètes : interface, RPC, oracles, opérateurs et garde.

## Marchés : instantané, pas prévision

API [CoinGecko, marchés BTC/ETH/SOL](https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=bitcoin,ethereum,solana&per_page=3&page=1), données des trois actifs au **12 novembre 2026, 11:26:58 UTC** : capitalisations **1 473,35 Md USD**, **249,30 Md USD**, **48,97 Md USD** (arrondies à deux décimales). Les valeurs originales, images et horodatages sont conservés dans `assets/data/`.

API [CoinGecko, total global](https://api.coingecko.com/api/v3/global), mise à jour **11:26:21 UTC** : **2 430,47 Md USD**, soit environ **2,43 billions USD** au sens français. Couverture et méthodologie sont celles du fournisseur. Le graphique est un instantané statique : aucun appel API pendant la projection. La capitalisation n’est ni une trésorerie disponible, ni une liquidité, ni le chiffre d’affaires des solutions blockchain, ni une mesure d’adoption métier.

## Usages et institutions

- [BCE, bilan des travaux exploratoires 2024, publié en juin 2025](https://www.ecb.europa.eu/press/pubbydate/2025/html/ecb.exploratoryworknewtechnologies202506.en.html) : **64 participants**, près de **1,6 Md€** réglé en monnaie de banque centrale ; distinguer essais réels et expériences en environnement de test. La Banque de France fournit **DL3S**, l’une des trois solutions d’interopérabilité étudiées. Les montants sont ceux de l’ensemble Eurosystème, pas de la seule Banque de France.
- [Banque de France, deuxième rapport d’expérimentations, 2023](https://www.banque-france.fr/fr/communiques-de-presse/la-banque-de-france-publie-un-second-rapport-pour-partager-ses-lecons-tirees-de-ses-experimentations) : programme de MNBC de gros lancé en 2020, douze expérimentations à cette date.
- [Banque de France / Eurosystème, lancement de Pontes, **21 septembre 2026**](https://www.banque-france.fr/fr/communiques-de-presse/leurosysteme-introduit-la-monnaie-de-banque-centrale-dans-la-finance-tokenisee) : règlement de gros pour actifs tokenisés, accès progressif ; mise en œuvre complète attendue d’ici 2028. Appia vise un schéma directeur d’ici 2028. Ces horizons sont des objectifs annoncés ; ils ne sont pas présentés comme des résultats déjà livrés. L’euro numérique de détail est un sujet distinct.
- [EBSI, registres d’émetteurs et schémas, mise à jour du 30 septembre 2026](https://hub.ebsi.eu/docs/services/trust-chains-and-trusted-issuers) : accréditation et vérification de justificatifs. Un justificatif vérifiable n’exige pas d’être un NFT ; le registre de confiance est distinct du document remis à la personne.
- [Maersk / IBM, arrêt annoncé de TradeLens, **29 novembre 2022**](https://www.maersk.com/news/articles/2022/11/29/maersk-and-ibm-to-discontinue-tradelens) : collaboration sectorielle et viabilité commerciale insuffisantes selon l’annonce ; arrêt visé au premier trimestre 2023. Ce cas ne constitue pas un diagnostic de défaut cryptographique.
- [CNIL, Blockchain et RGPD, **20 septembre 2018**](https://www.cnil.fr/fr/technologies/blockchain-et-rgpd-quelles-solutions-pour-un-usage-responsable-en-presence-de-donnees-personnelles) : choix technologique, responsabilités et protection des données dès la conception. Les données personnelles et justificatifs sensibles ne sont pas assimilés à des éléments librement publiables dans le registre.

Les diagrammes métier et le lot 17 sont des exemples pédagogiques. Ils ne reproduisent pas une infrastructure réelle de la Banque de France, de Maersk ou d’un client.
