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

## Creation du compte Azure Cosmos DB

Depuis le portail [Azure](https://portal.azure.com), cliquez sur "**Create a resource**"

![sparkle](Pictures/006.png)

Recherchez le service Azure Cosmos DB

![sparkle](Pictures/007.png)

Puis cliquez sur le bouton "**Create**"

![sparkle](Pictures/008.png)

Sélectionnez le groupe de ressources créé précédement, définissez les options dont vous avez besoin puis cliquez sur le bouton "**Review + create**"

![sparkle](Pictures/009.png)

Cliquez sur le bouton "**Create**"

![sparkle](Pictures/010.png)

Une fois le compte Azure Cosmos DB créé, cliquez sur le bouton "**Go to resource**" afin de créer une base et un containeur.

![sparkle](Pictures/011.png)

Cliquez sur "**Overview**" puis sur "**Add Container**"

![sparkle](Pictures/012.png)

Créez une nouvelle base de données ainsi qu'un nouveau containeur. Dans cet exemple nous allons décocher la case "**Provision database throughput**" (mais le script fonctionnera aussi avec cette case cochée).

Cliquez sur le bouton "**Ok**"

![sparkle](Pictures/013.png)

Une fois la base et le containeur créés, ils devront être visibles depuis la vue d'ensemble de votre compte Azure Cosmos DB 

![sparkle](Pictures/014.png)

## Création du Service Azure Automation

Depuis le portail [Azure](https://portal.azure.com), cliquez sur "**Create a resource**"

![sparkle](Pictures/015.png)


Puis recherchez "**Automation**"

![sparkle](Pictures/016.png)

Cliquez sur le bouton "**Create**

![sparkle](Pictures/017.png)

Donnez un nom à votre compte "*Automation*", choisissez le groupe de ressources créé précédement et sélectionnez "**Yes**" pour "**Create Azure Run As account**"

Cliquez sur le bouton "**Create**"

![sparkle](Pictures/018.png)

Après la création du compte "*Azure Automation*", vous devriez donc avoir les ressources suivantes dans votre groupe de ressources

![sparkle](Pictures/019.png)

## Paramètrage du compte Azure Automation

Cliquez sur votre compte **Azure Automation**

![sparkle](Pictures/020.png)

Cliquez sur "**Runbooks**" puis sur "**Create a runbook**"

![sparkle](Pictures/021.png)


