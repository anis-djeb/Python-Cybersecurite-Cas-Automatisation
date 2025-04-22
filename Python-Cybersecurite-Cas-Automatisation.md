# Projet d'automatisation des tâches en Python

## Scénario 1 : Automatiser le processus de connexion

L'équipe d'analystes sécurité de XYZ vous demande d'automatiser le processus de connexion. L'objectif est d'éviter aux administrateurs une validation manuelle.

Liste des utilisateurs et appareils autorisés :
| Utilisateurs | Appareils |
|--------------|-----------|
| keith        | 789uk     |
| john         | jfklsdjf  |
| jimmy        | 9djflksf  |
| sarah        | 342dfsf   |

Si l'utilisateur est valide, afficher `Utilisateur autorisé`. Si l'appareil correspond, afficher `Appareil autorisé`, sinon `Appareil non autorisé`. Si l'utilisateur n'est pas valide, afficher seulement `Utilisateur non autorisé`.

### Solution :
```python
utilisateurs_valides = ["keith", "john", "jimmy", "sarah"]
appareils_valides = ["789uk", "jfklsdjf", "9djflksf", "342dfsf"]

def verifier_connexion(utilisateur, appareil):
    if utilisateur in utilisateurs_valides:
        print("Utilisateur", utilisateur, "autorisé.")
        index = utilisateurs_valides.index(utilisateur)
        if appareil == appareils_valides[index]:
            print("Appareil", appareil, "autorisé pour", utilisateur)
        else:
            print("Appareil", appareil, "non autorisé.")
    else:
        print("Utilisateur", utilisateur, "non autorisé.")

verifier_connexion("keith", "789uk")
verifier_connexion("john", "jfklsdjf")
verifier_connexion("albert", "3242394872")
verifier_connexion("sarah","342dfsf")
verifier_connexion("Jimmy", "9djflksf")
verifier_connexion("keith", "dkfjs")
```

## Scénario 2 : Analyse des connexions

Analyser les connexions et afficher une alerte si l'activité est inhabituelle (ratio > 3).

| Utilisateur | Connexions du jour | Moyenne quotidienne |
|-------------|--------------------|---------------------|
| keith       | 8                  | 4                   |
| john        | 7                  | 6                   |
| jimmy       | 6                  | 1                   |
| sarah       | 9                  | 2                   |

### Solution - Modèle 1 :
```python
utilisateurs = ["keith", "john", "jimmy", "sarah"]
connexions_aujourdhui = [8, 7, 6, 9]
connexions_moyennes = [4, 6, 1, 2]

def analyser_connexions(utilisateur, connexions_jour, moyenne):
    if utilisateur in utilisateurs:
        index = utilisateurs.index(utilisateur)
        print("Utilisateur :", utilisateur)
        if connexions_aujourdhui[index] == connexions_jour:
            print("Connexions aujourd'hui :", connexions_jour)
        else:
            print("Erreur connexions jour.")
        if connexions_moyennes[index] == moyenne:
            print("Moyenne quotidienne :", moyenne)
        else:
            print("Erreur moyenne quotidienne.")
    else:
        print("Utilisateur non reconnu.")

analyser_connexions("keith", 8, 4)
analyser_connexions("john", 7, 6)
analyser_connexions("jimmy", 6, 1)
analyser_connexions("Jimmy", 8, 7)
analyser_connexions("keith", 9, 5)
```

### Solution - Modèle 1 avec widget interactif :
Utilisation des widgets ipywidgets pour interaction utilisateur.

### Solution - Modèle 2 :
Affiche un ratio détaillé et des alertes.

```python
def analyser_connexions_avance(utilisateur, connexions_jour, moyenne):
    if utilisateur in utilisateurs:
        index = utilisateurs.index(utilisateur)
        print("Utilisateur :", utilisateur)
        if connexions_aujourdhui[index] != connexions_jour:
            print("Erreur connexions jour.")
            return
        if connexions_moyennes[index] != moyenne:
            print("Erreur moyenne quotidienne.")
            return

        ratio = connexions_jour / moyenne
        print("Connexions aujourd'hui :", connexions_jour)
        print("Moyenne quotidienne :", moyenne)
        print("Ratio :", ratio)
        if ratio > 3:
            print("ALERTE : activité anormale.")
    else:
        print("Utilisateur non reconnu.")

analyser_connexions_avance("john", 7, 6)
analyser_connexions_avance("jimmy", 6, 1)
analyser_connexions_avance("sarah", 9, 2)
analyser_connexions_avance("Sarah", 8, 3)
analyser_connexions_avance("sarah", 9, 1)
analyser_connexions_avance("sarah", 3, 2)
```

### Solution - Modèle 2 avec widget interactif :
Utilisation des widgets ipywidgets pour analyser dynamiquement les données utilisateur.

## Scénario 3 : Expressions régulières pour identifier motifs

Trouver :
- Signature hexadécimale
- Appareils commençant par "r15"
- Adresses IP valides (192.xxx.xxx.xxx)

### Solution :
```python
import re

# Signature hexadécimale
texte_signature = "La signature du malware est 0x9ACDAB et nécessite analyse."
signature = re.findall(r"0x[0-9A-Fa-f]+", texte_signature)
print("Signature trouvée :", signature)

# Appareils commençant par r15
texte_appareils = "r262c36 67bv8fy r151dm4 r15xk9h r15u9q5 r159r1u"
appareils_r15 = re.findall(r"r15\w+", texte_appareils)
print("Appareils r15 :", appareils_r15)

# Adresses IP valides
logs = ("eraab 2025-04-10 192.168.152.148 iuduike 192.168.22.115 smartell 192.168.190.178")
adresses_ip = re.findall(r"192\.\d{1,3}\.\d{1,3}\.\d{1,3}", logs)
print("Adresses IP valides :", adresses_ip)
```

### Analyse approfondie IP :
Identifier adresses IP suspectes.

```python
adresses_suspectes = ["192.168.190.178", "192.168.96.200", "192.168.174.117", "192.168.168.144"]
for ip in adresses_ip:
    if ip in adresses_suspectes:
        print("IP suspecte détectée :", ip)
    else:
        print("IP normale :", ip)
```