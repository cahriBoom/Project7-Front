# OC Library

Avec l’objectif de moderniser la gestion de ces bibliothèques.
À ce titre, plusieurs axes d’amélioration ont été identifiés dont la gestion des emprunt de livres via une application web et une base de donnée.  

## Présentation

Ce projet est un site web de gestion d'une bibliothèque il est divisé en 3 parties :
- Le BackEnd pour l'administrateur (Project7-Back)
- le FrontEnd pour les utilisateurs (Project7-Front)
- le Batch pour envoyer les rappels de retours de livres (Project7-Batch)


Ce projet est conçu sur **Windows**, en utilisant **Eclipse** comme outil de développement et **MySql** comme système de gestion de base de données.
**Apache Maven** est utilisé pour la gestion et l'automatisation de production des projets logiciels Java. Et le framework **Spring boot** est utilisé afin de facilité le développement de l'application.

### Pré-requis

- Windows 2010
- Java jdk version 
- MySQL version 
- un serveur Tomcat version XXX
- plusieurs instances de Apache Tomcat (minimum 3 instances)
- un gestionnaire de base de données SQL (MySQL Workbench, ...)

### Déploiement du projet
- Télécharger la version la plus récente d'Apache Tomcat.
- Telecharger Project7-Back, Project7-End, Project7-Batch dans votre environnement (ex : D:\Project7)
- Extraire les dossiers des archives : Project7-Back-main, Project7-Front-main,Project7-Batch-main

### Déploiement Tomcat
- Copier votre dossier Tomcat dans votre environnement
- Creer 3 sous-dossiers dans le dossier Tomcat : tomcat1, tomcat2, tomcat3
- Supprimer les contenus des dossiers 'bin' et 'lib' dans les sous-dossiers tomcat1,tomcat2 et tomcat3
- Créer 3 fichiers **.bat** dans le dossier **bin** de tous les dossier copiés. (startup.bat, shutdown.bat et setenv.bat) 
  avec les contenus définis ci-dessous (tomcatServer est le nom de votre dossier de votre serveur Tomcat) 

### **setenv.bat**
> set JAVA_HOME=< Chemin de votre variable d'environement JAVA>

### **startup.bat**
>@echo off
if "%OS%" == "Windows_NT" setlocal
cd ..
set "CATALINA_BASE=%cd%"
set "CATALINA_HOME=< chemin de votre serveur main tomcat >"
set "EXECUTABLE=%CATALINA_HOME%\bin\startup.bat"
call "%EXECUTABLE%" %*
>
### **shutdown.bat**
>@echo off
if "%OS%" == "Windows_NT" setlocal
cd ..
set "CATALINA_BASE=%cd%"
set "CATALINA_HOME=< chemin de votre serveur main tomcat >"
set "EXECUTABLE=%CATALINA_HOME%\bin\shutdown.bat"
call "%EXECUTABLE%" %*
>

>**NOTE :** A la ligne 3 de **shutdown.bat** et **startup.bat** il s'agit de 2 points et **NON** 3.

- Ensuite modifier les ports de chaque instances de serveur dans le fichier **/conf/server.xml**

>
    <Connector port="8080" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />
>
>
	<Connector port="8009" protocol="AJP/1.3" redirectPort="8443" />
>

>
	<Server port="8005" shutdown="SHUTDOWN">
>
Les trois instances doivent avoir des ports **différents**.


### Déploiement des fichiers WAR
- Importer le projet dans votre outil de développement (Eclipse, InteliJ, ...) en fichier **.war**
- Copier les fichiers .war dans **/webapps/** des sous-dossiers tomcat1,tomcat2 et tomcat3


### Démarrage des serveurs Tomcat
- Lancer une 'Invite de commandes' et naviguer jusqu'au dossier de chaque instance ou faites le manuellement.
- Lancer les 3 instances tomcat en exécutant le fichier **startup.bat**


### Création et Initilisation de la Base de données
- Ouvrir votre outil de gestion de base de données. (MySQL WorkBench,...)
- Créer la base de données à l'aide du fichier "LibraryDump.sql".
- Importer le jeu de données fournit dans "LibraryData.sql".


## Démarrage

Une fois l'installation terminée.

Lancez un navigateur web, et entrez l'adresse:
> [localhost:8081/libraryFront/accueil](http://localhost:8081/libraryFront/accueil)

## Développé avec

* [Eclipse] - Environement de développement
* [Tomcat] - Serveur Web
* [MySQL] - Base de données
* [MySQL Workbench] - Gestionnaire de base de données


## Auteurs
* **Maxime Cathala** _alias_ [@cahriBoom](https://github.com/cahriBoom)
# Project7-Front
