# Virtual Machines, Clones, and Templates

## Defining Virtual Machines

VM: simulation d'un machine physique

1. Emulation
2. Paravirtualisation
3. Full virtualisation

1 VM = 1 OS

1VM = plusieurs fichiers dans un datastore local disk ou SAN-based LUN

VM a des ressources dédié

## VM création

- from scratch
- import depuis .ovf (Open Virtualisation Format)
- clone
- Déploiement d'un template
- utiliser une machine existante

Elément Clé:

- Virtual hardware
- OS
- système d'application

Suivre les étapes pour la création d'une VM

A la création on paramètre les différentes options de la VM => on ne peut pas dépasser les limites de l'hôte

## Working with clones and templates

vSphere vCenter Inventory Views: dossier pour organiser l'inventaire:

- Groupe d'object
- Créer une hiérarchie
- Déléguer l'autorité
- Programmer les alarmes

A considérer:

- Droit d'accès
- Sécurité des actif
- Notification d'événement
- Besoin de management

VMs => convertir en templates = contient configuration VM

Suivre la procédure pour la conversion

VM convertie deviennent des temlates et non plus des VM utilisables

Clonage créer des copies exactes

Template => inmodifiable: passer par new VM pour modifier

Peut seulement customiser les Guest OS settings

## Advanced configuration

Création de snapshots possible

Permettre des tester des modifications

Suivre la procédure pour la création et la restauration

VMware a des plug-in => appliances

Des configurations prête à l'emploie => voire leur site

## vSphere vMA

ESXi seul n'a pas de service en console, solutions:

- vSphere Command-Line Interface (vCLI) => packet pour Windows ou Linux
- vSphere Management Assistant (vMA) => Linus Os tournant dans une VM
- vSphere PowerCLI => intergace pour vSphere API
- ESXi Shelle/Remote SSH Shell => pour de la réparation: activer avec DCUI dans vSphere Client