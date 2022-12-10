# SimpleText@CLEF-2022 Tâches

[Accueil](./) | [Appel à contribution](./CFP) | [Dates importantes](./dates) | [Tâches](./tasks)  | [Outils](./tools)  
[Programme](./program) | [Publications](./publications) | [Organisateurs](./organisers) | [Contact](./contact) | [CLEF-2023](https://simpletext-project.com/2023/clef)


---

## Directives pour les tâches SimpleText

Nous vous invitons à soumettre aussi bien des interventions automatiques que manuelles ! Les interventions manuelles doivent être signalées.

---

<button>[Accès](./tasks)</button> | <button>[Tâche partagée 1](./task1)</button> | <button>[Tâche partagée 2](./task2)</button> | <button>[Tâche partagée 3](./task3)</button>| <button>[Tâche non partagée 4](./task4)</button>


<br>

## Tâche 3 : Réécrivez ceci ! En fonction d'une requête, simplifiez des passages de résumés scientifiques. 

Le but de cette tâche est de fournir une version simplifiée de passages de texte (phrases) par rapport à une requête. Les participants recevront des requêtes et des résumés d'articles scientifiques. Les résumés peuvent être divisés en phrases. Les passages simplifiés seront évalués manuellement avec l'utilisation éventuelle de métriques d'agrégation.

**Format d'entrée :** 
Les données de formation et de test sont fournies aux formats JSON et CSV avec les champs suivants :
* *snt_id*: a unique passage (sentence) identifier
* *source_snt*: passage texte
* *doc_id*: a unique source document identifier
* *query_id*: a query ID
* *query_text*: simplification should be done with regard to this query

*Exemple de saisie :*

*{"snt_id":"G11.1_2892036907_2","source_snt":"With the ever increasing number of unmanned aerial vehicles getting involved in activities in the civilian and commercial domain, there is an increased need for autonomy in these systems too.","doc_id":2892036907,"query_id":"G11.1","query_text":"drones"}*

**Format de sortie:** 
Liste des termes à contextualiser dans un format **JSON** ou un fichier tabulé TSV (pour les exécutions manuelles) avec les champs suivants :
* *run_id*: Run ID starting with **team_id_task_3_**
* *manual*: Whether the run is manual {0,1}
* *snt_id*: a unique passage (sentence) identifier from the input file 
* *simplified_snt*: Text of the simplified passage 

*Exemple de sortie* :
{"run_id":"BTU_task_3_run1","manual":1,"snt_id":"G11.1_2892036907_2","simplified_snt":"Drones are increasingly used in the civilian and commercial domain and need to be autonomous."}

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
Les passages simplifiés seront évalués manuellement avec l'utilisation éventuelle de métriques d'agrégation.

### Soumission des résultats :
Les participants doivent placer leurs résultats d'exécution dans le dossier Documents créé pour leur utilisateur et **soumettre les résultats par e-mail** à *contact@simpletext-project.com*.

L'objet de l'e-mail doit être au format **\[CLEF TASK 3] TEAM_ID**. 

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
