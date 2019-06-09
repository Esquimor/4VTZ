# Managing Resources With vMotion and DRS

## Introduction to Resource Management

Les resources sont dynamique et imprévisible: CPU/Mémoire

Status de l'hôte peuvent changer: Failure/Maintenance/Test

vSphere solution:

- Pool de resources: alouer des resources aux VMs
- vMotion: Migrer VM d'un hôte à l'autre
- DRS: Load balancing avec le cluster

## Resource Pools

Resource Pool: vCenter objet qui aloue les resources et la mémoire

Définie sur un hôte ou un cluster

3 Attribues primaires:

- Shares: montant moyen qu'un objet à d'une resource
- Reservation: min somme de resources
- Limits: max

## vMotion

vMotion froide: migrer d'un hôte à l'aure => storage pas partager avec les ESXi

vMotion chaude: pas d'interruption => DAS storage disponible / plus lent

Hot migrations:

- hôte besoins:
  - CPU compatible
  - vMotion sur les 2 hôtes
  - accès au réseau physique
  - vSwith port group label identique
- VM besoins:
  - pas besoin spé du CPU
  - pas connection CD-ROME
  - pas conection vSwitch interne

Suivre la procédure d'installation

## Distributed Resource Scheduler (DRS)

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

## Pooling in a Cluster

Resource pool => subdivise le cluster

Tous les hôtes manager dans 1 cluster

Niveau plus fin de délégation de l'autorité

En mode maintenance DRS migre la VM vers un autre hôte