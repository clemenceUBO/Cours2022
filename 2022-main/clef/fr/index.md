# SimpleText@CLEF-2022 Accueil

---

[Accueil](./) | [Appel à contribution](./CFP) | [Dates importantes](./dates) | [Tâches](./tasks)  | [Outils](./tools)  
[Programme](./program) | [Publications](./publications) | [Organisateurs](./organisers) | [Contact](./contact) | [CLEF-2023](https://simpletext-project.com/2023/clef)
<!--- <img src="https://github.com/simpletext-madics/2021/blob/main/clef/FR.png?raw=true" width="30">https://simpletext-project.com/2022/clef/') --->

---

<img align="left" src="https://github.com/simpletext-madics/2021/blob/main/clef/simpletext-logo-blue.png?raw=true" width="100"/>  

## SimpleText: Simplification automatique des textes scientifiques


### Sujet et objectifs du laboratoire

SimpleText s'attaque aux défis techniques et aux difficultés d'évaluation en fournissant des données et des repères appropriés pour la simplification des textes.
<br/>Nous proposons les tâches suivantes :
* [TÂCHE 1   Qu'est-ce qui est dedans (ou dehors) ?](./task1)
Sélectionner les passages à inclure dans un résumé simplifié, à partir d'une requête.
* [TÂCHE 2   Qu'est ce qui n'est pas clair ?](./task2)
Étant donné un passage et une requête, classez les termes/concepts qui doivent être expliqués pour comprendre ce passage (définitions, contexte, applications,...). 
* [TÂCHE 3   Ré-écrivez ceci !](./task3)
En fonction d'une requête, simplifier des passages de résumés scientifiques. 
* [TÂCHE NON PARTAGÉE](./task4)
Toute proposition d'utilisation de nos données est la bienvenue !

Pour faire face à ces défis, SimpleText vise à répondre aux questions de recherche suivantes :
<br/>RQ1 - Quelle expression textuelle porteuse d'information doit être simplifiée (document et passage à inclure dans le résumé simplifié) ?
<br/>RQ2 - Quel type d'information de base devrait être fourni (quels termes devraient être contextualisés en donnant une définition et/ou une application) ? Quelles informations sont les plus pertinentes ou les plus utiles ?
<br/>RQ3 - Comment améliorer la lisibilité d'un texte court donné (par exemple en réduisant le vocabulaire et la complexité syntaxique) avec un taux acceptable de distorsion de l'information ?

### Importance pour le domaine et pertinence de CLEF

Avoir une culture scientifique est une aptitude importante pour les gens. C'est l'une des clés de l'esprit critique, de la prise de décision objective et du jugement de la validité et de la signification des résultats et des arguments, qui permet de discerner les faits de la fiction. Ainsi, posséder des connaissances scientifiques de base peut également contribuer à préserver sa santé, tant physiologique que mentale. La pandémie de COVID-19 en est un bon exemple. Comprendre le problème lui-même, connaître et appliquer les règles de distanciation sociale et les politiques sanitaires, choisir d'utiliser ou d'éviter tel ou tel traitement ou procédure de prévention peut devenir crucial. Dans le contexte d'une pandémie, l'information qualifiée et opportune doit atteindre tout le monde et être accessible. C'est ce qui motive des projets tels que [EasyCovid](https://easycovid19.org/).

Cependant, les textes scientifiques sont souvent difficiles à comprendre car ils nécessitent de solides connaissances de base et utilisent une terminologie délicate. Bien que des efforts aient été faits récemment pour simplifier les textes, l'élimination automatique de ces barrières de compréhension entre les textes scientifiques et le grand public reste un défi à relever. SimpleText Lab rassemble des chercheurs et des praticiens travaillant sur la génération de résumés simplifiés de textes scientifiques. Il s'agit d'un nouveau laboratoire d'évaluation qui fait suite à [l'atelier SimpleText-2021 Workshop](https://simpletext-project.com/2021/clef/en/). Toutes les perspectives sur la vulgarisation scientifique automatique sont les bienvenues, y compris mais sans s'y limiter : Le traitement du langage naturel (NLP), la recherche d'information (IR), la linguistique, le journalisme scientifique, etc.

### Scenarios

L'objectif est de créer un résumé simplifié de plusieurs documents scientifiques à partir d'une requête donnée, ce qui permet à l'utilisateur d'obtenir instantanément un résumé simplifié sur un sujet spécifique qui l'intéresse ou de générer un résumé quotidien, par exemple pour ArXiv.

### Configuration, mesures et tâches de l'évaluation 

Ensemble de données : Nous utilisons [l'ensemble de données du réseau de citations](https://www.aminer.org/citation) : DBLP+Citation, ACM Citation network. Un index de recherche élastique est fourni aux participants, accessible via une API GUI. Cet index est adéquat pour :
- Appliquer des méthodes basiques de recherche de passage basées sur des modèles de RI vectoriels ou linguistiques.
- Générer des modèles d'allocation de Dirichlet latents,
- Entraîner des réseaux de neurones graphiques pour la recommandation de citations, comme c'est le cas dans Stellar Graph par exemple,
- Appliquer des transformateurs bidirectionnels profonds pour l'expansion de requêtes...

Les données sont de deux ordres : La *médecine* et l'*informatique*, deux domaines parmi les plus populaires dans les forums comme [ELI5](https://www.reddit.com/r/explainlikeimfive/).

Requêtes en anglais : Pour cette édition, les requêtes sont une sélection de titres de presse récents du Guardian enrichie de mots-clés extraits manuellement du contenu des articles. Il a été vérifié que chaque mot-clé permet d'extraire au moins 5 résumés pertinents. L'utilisation de ces mots-clés est facultative.
<br/>Format d'entrée pour toutes les tâches :
<br/>- Les sujets sont au format MD
<br/>- Articles en texte intégral du Guardian (lien, dossier avec les textes intégraux au format MD)
<br/>- Index ElasticSearch sur le serveur de données
<br/>- vidage complet du DBLP au format JSON.GZ
<br/>- Résumés DBLP extraits pour chaque sujet dans le format MD suivant (doc_id, année, résumé)

## Comment citer
Si vous étendez ou utilisez ce travail, veuillez citer [l'article](https://doi.org/10.1007/978-3-031-13643-6_28) où il a été présenté :
```
Liana Ermakova, Eric SanJuan, Jaap Kamps, Stéphane Huet, Irina Ovchinnikova, Diana Nurbakova, 
Sílvia Araújo, Radia Hannachi, Elise Mathurin, and Patrice Bellot. 2022. 
Overview of the CLEF 2022 SimpleText Lab: Automatic Simplification of Scientific Texts. 
In Experimental IR Meets Multilinguality, Multimodality, and Interaction: 13th International 
Conference of the CLEF Association, CLEF 2022, Bologna, Italy, September 5–8, 2022, Proceedings. 
Springer-Verlag, Berlin, Heidelberg, 470–494. https://doi.org/10.1007/978-3-031-13643-6_28
```
[Article](https://doi.org/10.1007/978-3-031-13643-6_28)

[Télécharger .BIB](../../BibTeX/ermakova_overview_2022.bib)

---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<img src="https://github.com/simpletext-madics/2022/blob/main/clef/en/clef_logo_2022.png?raw=true" width="150">](http://www.clef-initiative.eu/) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://github.com/simpletext-madics/2021/blob/main/clef/logo-clef-initiative.png?raw=true" width="200">
