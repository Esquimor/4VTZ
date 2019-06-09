# Working With Datastores

## Introduction to Datastores

Stockage utilisé dans 2 Buts:

- ESXi host
- VM virtual disk

Stockage:

- Local sur ESX host
- Interne/Extern ESH host
- En réseau

Différent options de stockage disponible: SANs, .vmdk file, etc

Datastore:

- VMFS file => partition disque, LUN ou NFS => NAS filer
- Abstraction du stockage physique

Formats: ESXi =>  

- VMFS 5:
  - performant en cluster
  - optimiser VM
  - accès direct machine
  - 64 hôtes VMFS
- NFS => NAS filer (dossier NAS)
  - stokage non-transactionnel
  - SAN-based LUNs ou dans le filer

Datastores créer sur les machines de stockage => on peut voir les différentes propriété de ces dernires

Suivre la procédure pour créer un Datastore

Considérations: VMFS datastores

- Large
  - \+ de VM
  - \+ fléxible
- Petite: \+ de performances

## Networked Storage (iSCSI)

iSCSI:

- Stockage \+ rapide
- utilise le réseau IP existant
- moins chère que Fibre Channel
- accède via iSCSI initiators

Ip-over-Ethernet prends la place du Fibre Channel SAN en backend

ESXi Server supporte Hardware/Software iSCSI initiators

iSCSI name: iqn.<year-mo>.<reversed_domain_name>:<unique_name>

iSCSI Discovery: Dynamic/Static

iSCSI security: Anonyme/ CHAP :protocole de sécurité

Suivre procédure de configuration iSCSI

## Network Sotrage Fibre Channel

ESXi demande => Fibre Channel Host bus Adapters et un SAN Fibre Channel 

- 1 ou pls Fibre Channel  switches
- Systéme de stockage
- Cuivre ou fibre optique

VMware intégre un multipathing (trajet multiple)

- Native MultiPathing (NMP)
- régle: dernière utiliser/ fixe /round robin

iSCSI => dédoublé

- 2 carte physique
- 2 vSwitches
- seulement un utiliser

On peut étendre un Lun tant qu'il reste de l'espace, sinon ajouter un nouveau LUN ou partition

Raw Device Mapping +> Vm accès LUN sur l'hôte => accès direct à certaine fonctionnalité

Configuration:

- Virtual Compatibility Mode: accès au LUN via RDM => VMFS datastore
- Physical Compatibility Mode



Meilleur pratique:

- Réseau dédié: sécurité/vitesse
- spécifique LUNs => VM super utilisé
- Diviser le travail entre toutes les machines physique
- Production et test/dev séparer



De nouvelle fonctionnalités : Storage I/O control, VAAI