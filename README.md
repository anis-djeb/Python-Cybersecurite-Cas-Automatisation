# Projet d'automatisation des tâches en cybersécurité avec Python

> Ce projet est inspiré de la formation *Automatiser les tâches de cybersécurité avec Python*. Consultez ce [lien](https://www.coursera.org/learn/automatiser-les-taches-de-cybersecurite-avec-python) pour plus d'informations.

## Introduction

Ce projet se compose de trois scénarios développés et adaptés :
* Premièrement, automatiser le processus de connexion avec Python.
* Deuxièmement, analyser les connexions avec Python.
* Troisièmement, utiliser des expressions régulières pour détecter des motifs.

La solution complète est disponible dans le notebook `Python-Cybersecurite-Cas-Automatisation.md`.

## Scénario 1 : Automatiser le processus de connexion

L'équipe des analystes sécurité de l'entreprise XYZ vous demande d'automatiser le système de connexion afin que les administrateurs n'aient plus à valider manuellement chaque authentification.

Voici les données nécessaires à cette tâche :

* Liste des utilisateurs et appareils autorisés :

<div align="center">

| Utilisateurs | Appareils |
|--------------|-----------|
| keith        | 789uk     |
| john         | jfklsdjf  |
| jimmy        | 9djflksf  |
| sarah        | 342dfsf   |

</div>

* Si le nom d'utilisateur figure dans la liste, afficher `Utilisateur autorisé`.
* Si l'identifiant d'appareil correspond à celui attribué, afficher `Appareil autorisé`.
* Sinon, afficher `Appareil non autorisé`.
* Si le nom d'utilisateur est inconnu, afficher `Utilisateur non autorisé à accéder au système`.

⚠️ Faites attention à la casse du nom d'utilisateur.

## Solution 1 : Automatiser le processus de connexion

![Solution_1_1](https://github.com/anis-djeb/assets/blob/main/Python%20Cybersecurite%20Cas%20Automatisation/Screenshot_1.png)

## Scénario 2 : Analyser les connexions

L'équipe vous demande d'analyser les activités de connexion à l’aide de conditions, et d'automatiser le processus avec Python.

Objectif : afficher `Nombre de connexions aujourd'hui`, `Moyenne de connexions journalières`, et une `Alerte` si l'activité dépasse la normale.

Données utilisateur :

<div align="center">

| Utilisateur | Connexions aujourd'hui | Moyenne quotidienne |
|-------------|:----------------------:|:--------------------:|
| keith       | 8                      | 4                    |
| john        | 7                      | 6                    |
| jimmy       | 6                      | 1                    |
| sarah       | 9                      | 2                    |

</div>

* Si le `ratio de connexions` (connexions du jour / moyenne) dépasse 3, le système affiche une alerte.
* Utilisez `ipywidgets` pour afficher dynamiquement les résultats.
* Vous pouvez implémenter plusieurs méthodes pour analyser les connexions.
* Ordre de présentation attendu : Solution simple, Solution avec widget, Solution avancée, Widget avancé.

## Solution 2 : Analyser les connexions

![Solution_2_2](https://github.com/anis-djeb/assets/blob/main/Python%20Cybersecurite%20Cas%20Automatisation/Screenshot_2.png)

![Solution_2_3](https://github.com/anis-djeb/assets/blob/main/Python%20Cybersecurite%20Cas%20Automatisation/Screenshot_3.png)

![Solution_2_4](https://github.com/anis-djeb/assets/blob/main/Python%20Cybersecurite%20Cas%20Automatisation/Screenshot_4.png)

![Solution_2_5](https://github.com/anis-djeb/assets/blob/main/Python%20Cybersecurite%20Cas%20Automatisation/Screenshot_5.png)

## Scénario 3 : Utiliser les expressions régulières pour détecter des motifs

L'équipe souhaite que vous analysiez certaines structures dans les activités de sécurité, en utilisant Python et les expressions régulières.

Voici les objectifs à atteindre :

* Extraire la signature hexadécimale depuis cette phrase : `La signature du malware est 0x9ACDAB et nécessite analyse`.
* Identifier les identifiants d'appareils commençant par `r15` dans :  
  `r262c36 67bv8fy 41j1u2e r151dm4 1270t3o 42dr56i r15xk9h 2j33krk 253be78 ac742a1 r15u9q5 zh86b2l ii286fq 9x482kt 6oa6m6u x3463ac i4l56nq g07h55q 081qc9t r159r1u`
* Identifier les adresses IP de type `192.xxx.xxx.xxx` et analyser leur activité dans les logs suivants :

```
eraab 2025-04-10 6:03:41 192.168.152.148
niuduike 2025-04-09 6:46:40 192.168.22.115
smartell 2025-04-09 19:30:32 192.168.190.178
arutley 2025-04-12 17:00:59 1923.1689.3.24
rjensen 2025-04-11 0:59:26 192.168.213.128
aestrada 2025-04-09 19:28:12 1924.1680.27.57
asundara 2025-04-11 18:38:07 192.168.96.200
dkot 2025-04-12 10:52:00 1921.168.1283.75
abernard 2025-04-12 23:38:46 19245.168.2345.49
cjackson 2025-04-12 19:36:42 192.168.247.153
jclark 2025-04-10 10:48:02 192.168.174.117
alevitsk 2025-04-08 12:09:10 192.16874.1390.176
jrafael 2025-04-10 22:40:01 192.168.148.115
yappiah 2025-04-12 10:37:22 192.168.103.10654
daquino 2025-04-08 7:02:35 192.168.168.144
```

## Solution 3 : Détection de motifs

![Solution_3_6](https://github.com/anis-djeb/assets/blob/main/Python%20Cybersecurite%20Cas%20Automatisation/Screenshot_6.png)

![Solution_3_7](https://github.com/anis-djeb/assets/blob/main/Python%20Cybersecurite%20Cas%20Automatisation/Screenshot_7.png)

![Solution_3_8](https://github.com/anis-djeb/assets/blob/main/Python%20Cybersecurite%20Cas%20Automatisation/Screenshot_8.png)

![Solution_3_9](https://github.com/anis-djeb/assets/blob/main/Python%20Cybersecurite%20Cas%20Automatisation/Screenshot_9.png)
