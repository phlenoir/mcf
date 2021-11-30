# Monitoring

## Introduction

Pour obtenir une vue complète de l'état des plates-formes et des systèmes il y a trois chose à observer : les journaux(logs), les traces et les métriques.

Les métriques sont des indicateurs chiffrés de l'état des différents composants d'un point de vue technique ou métier. Une métrique mesure donc des éléments comme la consommation CPU, le nombre de requêtes, l'utilisation de la mémoire ou du disque. Une métrique peut également avoir un sens métier comme le nombre de paniers validés sur un site de commerce en ligne.

Les journaux sont les différents messages que chacun des logiciels de la plate-forme fournit pour comprendre son comportement et détecter certaines situations inattendues. 

Les traces correspondent aux différentes données concernant le flux des requêtes de bout en bout. Ainsi il sera possible de reconstituer le chemin d'une requête sur les différents tiers de la plateforme pourvu que les fichiers de logs soient produits avec un niveau de détail suffisant et qu'ils contiennent le moyen de corréler les différents messages entre eux. Par exemple, un client qui se connecte sur un service http va provoquer la génération d'un message dans les logs du serveur http, dans les logs du serveur applicatif, dans les logs du serveur de base de données, etc. En corrèlant ces messages entre eux, et en analysant les timestamps, on sera capable de mesurer le temps pris pour traverser chaque couche logicielle et détecter où se produisent les ralentissements.

## Solutions commerciales

Ce sont des solutions, comme Dynatrace ou AppDynamics, qui fournissent ces éléments de la manière la plus automatisée possible, notamment pour la partie trace. Ces solutions vont donc proposer les librairies nécessaires à l'instrumentation du code et par là se limite aux langages qui permettent l'inclusion de plug-in, comme le java par exemple.

## Solution ad-hoc

C'est l'objectif de notre prototype qui démontre la faciliter de produire des mesures et des statistiques à partir des messages de logs IIS. La génération des traces n'est pas prise en compte ici, car elle doit faire l'objet d'un développement complémentaire au niveau du code applicatif.
