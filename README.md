# Dashbord
## Impact des habitudes de sommeil sur certaines maladies

L’étude de l’impact des habitudes de sommeil sur les maladies s’inscrit dans plusieurs
domaines d’application, principalement dans les secteurs de la santé publique, de la recherche
médicale et de la prévention des maladies.

Afin de garantir la pertinence et la fiabilité des données utilisées dans cette étude, j'ai
avons choisi PubMed comme source principale d’information. PubMed est l’un des principaux
moteurs de recherche en biologie et en médecine au niveau mondial. Il offre un accès gratuit à la
base de données MEDLINE/NCBI, qui regroupe un vaste ensemble de références et de résumés
d’articles de recherche biomédicale. L’exploitation de cette source me permettra d’accéder à des
publications scientifiques de qualité, essentielles pour mener une analyse rigoureuse et fondée sur
des preuves.

## Méthodologie de collecte

L'extraction des articles sera réalisée via du **web scraping** en raison des limitations
imposées par l’API PubMed. 

Le fichier python **scraping.ipynb** contiendra le script pour l'automatisation de l'extraction des articles scientifiques, en utilisant les bibliothèques **BeautifulSoup** et **Requests**. \

### Définition des critères de recherche
Nous avons ciblé les articles contenant des mots-clés liés au sommeil et à certaines maladies dans leur titre, résumé ou mots-clés. \

Ce qui nous donne une équation sous la forme suivante : \

**(sleep habits OR sleep patterns OR sleep quality) AND (Alzheimer's disease OR cognitive decline OR dementia) AND (20013:2025[dp])** \

Cette équation de recherche nous permet donc de cibler les articles pertinents sur la période
de 2013 à 2025 pour la maladie d’Alzheimer. \

Pour le reste des maladies il a suffit de remplacer la partie de l’équation concernant la
maladie par des mots-clés suivants :
**● Obésité : Obesity**
**● Cancer : ("Cancer" OR "tumor" OR "carcinoma")**
**● Hypertension Arterielle : ("hypertension" OR "high blood pressure" OR "arterial hypertension")**
**● Diabete : ("Diabetes" OR "Type 2 Diabetes" OR "T2D")** \

Notons que pour le diabète, nous avons précisé le type 2 car le diabète de type 1 peut parfois
être présent dès la naissance. \

**Scraping des pages de résultats**
**● PubMed affiche 10 articles par page et impose une limite de 10 000 articles par recherche**
**● Pour contourner cette contrainte, nous avons découpé la collecte par intervalles de pages, en ajustant dynamiquement les requêtes pour récupérer le maximum d’articles.** \

### Filtrage des articles par date \

**● Nous avons observé un nombre très limité d’articles avant 2013, ce qui aurait pu biaiser notre analyse.**
**● Par conséquent, nous avons restreint notre collecte aux articles publiés à partir de 2013 pour garantir un corpus suffisamment représentatif.** \

### Extraction des métadonnées : Pour chaque article, nous avons récupéré \

**● Titre**
**● Lien**
**● Résumé**
**● Auteurs (nom, affiliation)**
**● Année de publication**
**● Mots-clés (extraits lorsqu’ils étaient disponibles)**

## Stockage des données :  \

Les articles collectés ont été sauvegardés dans un fichier CSV afin de faciliter leur exploitation et leur prétraitement dans les phases ultérieures.
