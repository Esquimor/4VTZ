## Capex/Opex

Les **OPEX** ou **dépenses d'exploitation** (de l'anglais *operational expenditure*) sont les charges courantes pour exploiter un produit, une entreprise, ou un système. Les **CAPEX** ou **dépenses d'investissement** (de l'anglais *capital expenditure*) se réfèrent aux immobilisations, c'est-à-dire aux dépenses qui ont une valeur positive sur le long terme.

## DRS

### Distributed Resource Scheduler (DRS)

DRS balance les resources dynamiquement:

- override resource pool policies
- VM meilleur endroit
- Balance VM sur les hôtes

Etapes:

1. activer vMotion
2. créer un cluster
3. activer DRS
4. ajouter les hôtes

3 niveaux:

- Manuel
- Partiellement automatisé
- Complétement automatisé

VM peuvent avoir un niveau de granularité supérieur:

- Affinity: VM et hôte ensemble
- Anti-Affinity: VM et hôte séparable
- Host affinity: VM avec hôte spécifique

Designer pour réduire les besoins en resources des datacenter

Besoin:

- Cluster manager par vCenter
- hôte équiper avec: WOL, IPMI ou iLO

VMware permet aussi d'appliquer DRS au stockage = SDRS

## Si 2 règles s'appliquent à un seul users laquelle s'applique ?

Si pas de restrictions il prend les 2, si y'en a il prends la règle la plus restrictive

## Qu'est ce qu'un esxi ?

Un serveur ESXi est un hyperviseur qui permet de consolider, mutualiser les ressources et créer des machines virtuelles.

Reduction des couts d'infrastructure

## vswitch

Dans une architecture classique, nous utilisons des vSwitchs (commutateurs virtuels standard), qui permettent les échanges réseaux entre les machines virtuelles au niveau de chaque hyperviseur.
Un commutateur réseau standard, virtual switch, ou vSwitch, est responsable de la connexion des machines virtuelles à un réseau virtuel. Un vSwitch fonctionne de manière similaire à un commutateur physique – avec quelques restrictions – et contrôle la façon dont les machines virtuelles communiquent les unes avec les autres.
Le vSwitch utilise les cartes réseau physiques (pNICs) associées avec le serveur hôte pour connecter le réseau virtuel au réseau physique. Avec vSphere, ces cartes réseau physiques sont également appelés adaptateurs de liaison montante (uplink adapters). Ces uplink utilisent des objets virtuels appelés vmnics, ou virtual network adapters, interfacés avec le vSwitch.

## type de datastore

Les datastores, ou banque de données, sont des conteneurs logiques qui masquent les caractéristiques propres à chaque périphérique de stockage. Elles sont caractérisées par une partition d’un volume formaté selon un certain système de fichier. Une seule banque de données ne peut reposer sur plusieurs systèmes de fichiers différents. Qui plus est, une seule LUN (espace logique) ne peut contenir qu’un seul volume VMFS.

- ISCSI (disque LUN)
- FibreChannel
- SAN (Réseau stockage dédié) 

## iscsi c quoi comme type de stockage

iSCSI est une abréviation de Internet Small Computer System Interface. C'est un protocole de stockage en réseau basé sur le protocole IP destiné à relier les installations de stockage de données.

## virtualization



## VMFS Virtual Machine File System (VMFS)

système de fichiers en cluster de VMware. Il a été développé pour stocker des images de disque de machine virtuelle, y compris des instantanés.

## pool de ressource

Un pool de ressource Vmware est un agrégat des ressources physiques des hôtes en termes de cpu et de mémoire qui peuvent être alloués aux machines virtuelles hébergées dessus. Plutôt qu’une machine ne puise utiliser que les ressources de son hôte, elle pourra utiliser toutes les ressources du pool de ressources d’hôtes mises à disposition. Cela permet également de répartir la charge et d’équilibrer l’utilisation des ressources des hôtes en plus de pouvoir définir des priorités/seuil pour chaque machines virtuelles et utilisateurs.

Ces pools de ressources peuvent apporter les avantages suivants :

-Isolation de performance : Permet d’empêcher les machines virtuelles de monopoliser les ressources d’un hôte.

-Utilisation efficace : Permet d’utiliser au mieux les ressources disponible d’un hôte, par exemple si un hôte du pool de ressource à une charge moins élevée, il va prendre automatiquement en charge les prochaines actions à effectuer.

## desktop virtualization / server virtualization

## vm kernel

VMkernel est un système d'exploitation de type POSIX développé par VMware. 

Le VMkernel est la liaison entre les machines virtuelles (VM) et le matériel physique qui les prend en charge.  