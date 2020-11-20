# Azure Cosmos DB : Pilotez les RU avec Azure Automation

Dans le scénario suivant, nous avons besoin d'ingérer et traiter une grande quantité d'information durant une période précise de la journée.
Etant donné que ce traitement se fait de manière récurrence et prédictible, il est donc aisé de planifier le changement de RU avec un service comme Azure automation.

Nous allons voir en détail comment mettre en place une solution avec Azure Automation pour effectuer ces changements de RU en fonction de nos besoins

## Prérequis

- [Un abonnement Azure](https://azure.microsoft.com/fr-fr/free/)


# Création des services Azure
## Création d'un groupe de ressources
Nous allons commencer par créer un groupe de ressources afin d'héberger les différents services de notre solution.

Depuis le portail [Azure](https://portal.azure.com), cliquez sur "**Create a resource**"

![sparkle](Pictures/001.png)

 Puis, recherchez "**Resource group**"

 ![sparkle](Pictures/002.png)


Cliquez sur le bouton "**Create**"

![sparkle](Pictures/003.png)

Donnez un nom au groupe de reessources puis cliquez sur le bouton "**Review + create**"

![sparkle](Pictures/004.png)

Puis validez la création en cliquant sur le bouton "**Create**"

![sparkle](Pictures/005.png)

