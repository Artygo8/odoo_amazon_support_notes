# Settings > Account-info (> Dashboard)

A configurer au mooment de la configuration du compte.

# Deposit Method

Compte en banque. On passe sur la carte de crédit.
Le compte pro coute 40eu par mois.
Compte particulier qui vend à perte...

# Avant, les comptes clients étaient devs.

https://www.odoo.com/documentation/15.0/applications/sales/sales/amazon_connector/setup.html

# dans Amazon Marchands

Menu Burger > manage your apps
Add `Odoo SA + Developer ID`

# Dans Odoo

-> On copie `Seller ID + Authorization token` dans Odoo.
Sales > configuration > checkbox Amazon (install)
Amazon Account > on peut en créer plusieurs (ex: Europe)

## Amazon account

Sign-up Marketplace.
On peut ajouter/supprimer/resync un Marketplace. (domaine dynamique)


## Amazon account > Order Followup

Sale Person / company + Last_order_sync (on sync que les derniers orders)
Attention, si on sync à partir d'avant, ça peut mener à des situations bizarres... (peut résoudre des problème de synchros)
(c'est basé sur `Amazon Order Ref`, donc ça évite les dups)
La date est basée sur le dernier changement de status d'un order (15 min entre création et premier status (avant c'est invisible (draft))).

## SCU

Est-ce qu'un de mes produits a ce SKU comme internal référence ? Si non il crée Amazon Sale Product (archivés par défault).
Il peut mettre des SKU sur ses internal references.
Le produit est lié à un SKU qui se modifie tout seul, mais on peut le remodifier.

## Setting Sales

Cocher Lock sale pour avoir accès au bouton unlock.

## On peut dupliquer les Amazon Account Config, si on veut spécialiser par sale teams.


# Amazon

## SKU

STOCK KEEPING UNIT -> Dépend de l'offre, et pas du produit.
/!\ Clé de matching entre Odoo et Amazon.
Plusieurs Orders peuvent avoir le même ASIN.
Order Item Id -> amazon_order_ref - amazon_item_ref

## Bougies -> 30 cents de commission amazon.

On en a pour 9euros pour amazon pour le Scale-Up! game de Odoo (28euros).

## Manage inventory

### Préférences + columns hidden

Cocher `Your minimum price + Your maximum price`

## Manage Orders

2 types de shipping:

### FBA VS MFN (2 pages)

Gift Wrapping + Shipping (no SKU mais équivalent)
Quand on fait une vente, ça fait une authorisation sur la carte de crédit. (ça bloque le montant) On peut toujours supprimer. Le prélèvement est fait lorsqu'Amazon expédie le produit.

# Amazon MWS Scratchpad

Permet de tester les flows.


# Taxes

Il faut configurer les bonnes taxes. Parce qu'on ne peut pas se permettre d'utiliser les taxes envoyées par Amazon (elles sont trop imprécises).
Avec Taxcloud, ça peut aussi foutre la merde...

On fait confiance au % de la taxe, et au montant avec la taxe, puis on recalcule le montant sans la taxe.


# Notes

Tous les champs sont READONLY.
En général on a 1 produit par order, parce que les gens achètent à plusieurs endroits.
On ne synchronize que d'Amazon a Odoo pour les cancelled actions.

On supporte pas Amazon CHN, et il y a des marketplaces à peu près supportés, mais seulement quelques marketplaces sont totalement supportés.
Dépend de la TVA active ou non.
