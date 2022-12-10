# SimpleText@CLEF-2022 Tâches

[Accueil](./) | [Appel à contribution](./CFP) | [Dates importantes](./dates) | [Tâches](./tasks)  | [Outils](./tools)  
[Programme](./program) | [Publications](./publications) | [Organisateurs](./organisers) | [Contact](./contact) | [CLEF-2023](https://simpletext-project.com/2023/clef)


---

## Directives pour les tâches SimpleText

Nous vous invitons à soumettre aussi bien des interventions automatiques que manuelles ! Les interventions manuelles doivent être signalées.

---

<button>[Accès](./tasks)</button> | <button>[Tâche partagée 1](./task1)</button> | <button>[Tâche partagée 2](./task2)</button> | <button>[Tâche partagée 3](./task3)</button>| <button>[Tâche non partagée 4](./task4)</button>

<br>

## Tâche 2 : Qu'est-ce qui n'est pas clair ? Étant donné un passage et une question, classez les termes/concepts qui doivent être expliqués pour comprendre ce passage (définitions, contexte, applications,...).

L'objectif de cette tâche est de déterminer quels termes (jusqu'à 5) nécessitent une explication et une contextualisation pour aider un lecteur à comprendre un texte scientifique complexe - par exemple, en ce qui concerne une requête, les termes qui doivent être contextualisés (avec une définition, un exemple et/ou un cas d'utilisation). 
Pour chaque passage, les participants doivent fournir une liste classée des termes difficiles avec les notes correspondantes sur l'échelle 1-3 (3 pour les termes les plus difficiles, tandis que le sens des termes notés 1 peut être déduit ou deviné) et sur l'échelle 1-5 (5 pour les termes les plus difficiles). 
Les passages (phrases) sont considérés comme indépendants, c'est-à-dire que la répétition de termes difficiles est autorisée. Le regroupement des termes et des mesures automatiques (précision de la classification binaire des termes, NDCG pour le classement des termes, statistiques de kappa...) seront utilisés pour évaluer ces résultats.

**Format d'entrée :** 
Les données de formation et de test sont fournies aux formats JSON et CSV avec les champs suivants :
* `snt_id`: un identifiant unique de passage (phrase)
* `source_snt`: texte de passage
* `doc_id`: he sole source document identify
* `query_id`: un ID de requête
* `query_text`: les termes difficiles doivent être extraits des phrases en rapport avec cette requête

*Exemple de saisie :*

```
{"snt_id":"G06.2_2548923997_3",
"source_snt":"These communication systems render self-driving vehicles vulnerable to many types of malicious attacks, such as Sybil attacks, Denial of Service (DoS), black hole, grey hole and wormhole attacks.",
"doc_id":2548923997,
"query_id":"G06.2",
"query_text":"self driving"}
```

**Format de sortie :** 

Liste des termes à contextualiser dans un format **JSON** ou un fichier tabulé TSV (pour les exécutions manuelles) avec les champs suivants :
* `run_id`: Run ID commençant par **team_id_task_id_**
* `manual`: Si l'exécution est manuelle {0,1}
* `snt_id`: un identifiant unique de passage (phrase) à partir du fichier d'entrée 
* `term`: Terme ou autre expression à expliquer
* `term_rank_snt`: rang de difficulté du terme dans la phrase donnée
* `score_5`: score de difficulté des termes sur une échelle de 1 à 5 (5 étant les termes les plus difficiles)
* `score_3`: score de difficulté des termes sur une échelle de 1 à 3 (3 étant les termes les plus difficiles)

*Exemple de sortie* :

```{json}
{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"term":"black hole attack",
"term_rank_snt":1,
"score_5":5,
"score_3":3},

{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"term":"grey hole attack",
"term_rank_snt":2,
"score_5":5,
"score_3":3},

{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"term":"Sybil attack",
"term_rank_snt":3,
"score_5":5,
"score_3":3},

{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"term":"wormhole attack",
"term_rank_snt":4,
"score_5":5,"score_3":3},

{"run_id":"NP_task_2_run1",
"manual":1,
"snt_id":"G06.2_2548923997_3",
"term":"Denial of service attack",
"term_rank_snt":5,
"score_5":4,
"score_3":3}
```

*Vérificateur du format de sortie*

Vous pouvez utiliser ce script python3 pour vérifier le format de sortie. Ce script nécessite Python 3 et la bibliothèque Pandas :
[Télécharger python output checker](../check_format.py)

**Disclaimer :** En téléchargeant et en utilisant ces données, vous acceptez les conditions d'utilisation. Toute utilisation des données à des fins autres que la recherche universitaire constituerait une violation de l'utilisation prévue de ces données. 

Par conséquent, en téléchargeant et en utilisant ces données, vous donnez les assurances suivantes concernant les données SimpleText :
1. Vous n'utiliserez pas et ne permettrez pas à d'autres d'utiliser les données dans les ensembles de données SimpleText de quelque manière que ce soit, sauf pour les cours et la recherche universitaire.
2. Vous ne divulguerez, ne donnerez ou ne transmettrez à aucun moment (de quelque manière ou forme que ce soit ou à quelque fin que ce soit) les données (ou toute partie de celles-ci) à tout endroit ou personne, y compris, mais sans s'y limiter, la mise à disposition des données sur Internet et la copie des données sur tout système de stockage basé sur le cloud.
3. Vous ne libérerez pas et ne permettrez pas à d'autres de libérer l'ensemble des données ou toute partie de celles-ci à toute personne. 

En cas de violation des conditions d'accès aux données à des fins scientifiques, cet accès peut être retiré à l'entité de recherche et/ou au chercheur. L'entité de recherche peut également être tenue de payer des dommages et intérêts à des tiers ou être invitée à prendre des mesures disciplinaires à l'encontre du chercheur fautif. 


### Évaluation
Le regroupement des termes et les métriques automatiques (précision de la classification binaire des termes, NDCG pour le classement des termes, statistiques de kappa...) seront utilisés pour évaluer ces résultats.

### Soumission des résultats :
Les participants doivent placer leurs résultats d'exécution dans le dossier Documents créé pour leur utilisateur et **soumettre les résultats par e-mail** à *contact@simpletext-project.com*.

L'objet de l'e-mail doit être au format **\[CLEF TASK 2] TEAM_ID**. 

Les runs doivent être soumis sous forme de <ins>Dossier ZIP des fichiers JSON correspondants</ins>. Les exécutions manuelles peuvent être soumises au format CSV. 

Un courriel de confirmation sera envoyé dans les deux jours suivant la date limite de soumission. 

## Comment citer
Si vous étendez ou utilisez ce travail, veuillez citer l'[article] (https://doi.org/10.1007/978-3-031-13643-6_28) où il a été présenté :
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
