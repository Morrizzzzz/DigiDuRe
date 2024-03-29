# DigiDuRe
This repository contains code and scripts developed for the [Digital Dutch Religion Portal 1500-2000 project](https://research-software-directory.org/projects/digidure) a project that has been a collaboration between the [Vrije Universiteit Amsterdam, Faculity of Humanities, HDC](https://vu.nl/nl/over-de-vu/diensten/universiteitsbibliotheek/meer-over/collectie-hdc-protestants-erfgoed]) and the [Netherlands eScience Center](www.esciencecenter.nl). The main researcher from the VU is [prof. dr. Fred van Lieburg](https://research.vu.nl/en/persons/fred-van-lieburg), the lead research software engineer is [Dr. Maurice de Kleijn](https://www.esciencecenter.nl/team/dr-maurice-de-kleijn/).

The project aims to map long-term developments in Dutch public discourse, especially in religion. An analysis of book titles and connected meta-data with multiple other data sources should deliver a bottom-up reconstruction of trends and changes in thematization. To do so four main activities are defined.


![Figure 1 shows a schematic overview on the various activities.](/images/figure1.png)
*Overview of the various activities in DigiDuRe*

## 1. Data Harmonzation - Protestant individuals
A structured dataset with carreers of protestant ministers from 1500 until 2000 is created out of a series of semi-structured datasources that are the result of archival historical research. This process is considered data harmonization and entails the modelling of the data structure and a series of processing steps to translate the data from the one format / structure to the other. This results in a new dataset named CLERUS - Database Dutch Reformed Clergy.

As for the process of converting the semi-structured dataset into a structured database the first step is to generate a datamodel which allows to include the various fields that the various datasets have. From there, a series of processing steps are generated which translates the various document in different formats into the datamodel. The developed scripts are grouped under [1_Data_Harmonization](/1_Data_Harmonization/).

The harmonized dataset CLERUS is initially processed and stored as a relational database. The data analyses on the data are conducted using the data in this format. Yet, in order to make the dataset available as linke data, a mapping towards LOD will be published as part of the project as well.

To link book title dataset with CLERUS we have decided to extract the data from the Royal library´s Linked Data (SPARQL) endpoint and translate it into a relational database. The main reason for this, is that digital skill level of the target audience does not match with the required skill level needed for using Linked Data. In addition, the history scholars that are participating in this project want to be able to store the dataset locally and have the opportunity to manipulate it. [2_Linking_data](/2_Linking_data/) thus exists of a script that allows downloading data from the Royal Libraries´ SPARQL endpoint to extract a selection form the the Short-Title Catalogue Netherlands ([STCN]( http://data.bibliotheken.nl/doc/dataset/stcn)) dataset and the ([Nederlandse Bibliografie Totaal (NBT)](http://data.bibliotheken.nl/doc/dataset/nbt)).

## 2. Linking and enriching Data
In order to analyse book titles in relation to protestant persons (from CLERUS), datasets need to be linked. Linking datasets with each other is on the one hand a technical challenge. It entails making sure that the various file formats communicate with each other. On the other hand it is the challenge of linking records with each other. For example, for names the combination of surname, firstname and infix are often considered unique, however not every dataset has this combination stored in the same way. Also, variety in name spellings and individuals having the same name forms a challenge when attempting to connect datasets.

To connect data from the Dutch Biography Portal ([BP](http://www.biografischportaal.nl/)) a script has been developed under [2_Linking_data](/2_Linking_data/). In addition, a script has been developed that allows to link CLERUS with the Booktitles. Furthermore, a geocoding script has been developed to link the various mentioned placenames to real locations.


## 3. Data Analysis
Through the connection of the various datasets an analysis of book titles and connected meta-data can be performed which is anticipated to deliver a bottom-up reconstruction of trends and changes in thematization. Though many fields of history will benefit from work in digital history, the focus on religion will stimulate new insights in this subdiscipline. The analysis scripts can be found under [3_Data_Analysis](/3_Data_Analysis/)

## 4. Dissemination
A vital part of this project is also to train the history scholars in how to work with data. Therefore, the steps that have been taken in this project are well documented and training material has been produced in which certain concepts are introduced and explained.
Another aspect of the dissemination is that the data can be accessed in various formats. Therefore an additional script is developed to publish the data as linked data [1_Data_Harmonization](/1_Data_Harmonization/). The dissemination of the project is done in the form of this repository, furthermore [4_Dissemination](/4_Dissemination/) contains a series a workshop slides.


# Installation instructions
The scripts that are developed in the context of the project are mostly done in jupyter notebooks using python 3. The installation instructions and the the various packages that are used can be found under [4_Dissemination/install_packages.md](/4_Dissemination/install_packages.md)