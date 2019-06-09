# High Availability and Backups

## Traditional Backups

Système de backup sont installé sur chaque VM

Un serveur central controle et prépare les backups

Système trad. ne comprends pas les VMs => seulement les resources hôtes

## vStorage Apis for Data Protection (VADP)

- Pas de serveur proxy nécessaire
- Full, incrémental and différentiel backup
- Changed Block Tracking (CBT) => fast disk backup
- Backup => niveau fichier : Windows et Linux VMs

Plusieurs produits sont compatibles

Workflow:

1. Préparer la backup
2. Créer une snapshots
3. Envoyer les données à backup

VMware Data Recovery:

- jusqu'à 100 VMs
- CLI disponible
- appareil Linux séparer pour gérer les backup

=> Destinations des backups => vDisk, SMB/CIFs

VMware Data Protection:

- remplace VMware Data Recovery
- basé sur EMC's Avamar
- vCenter 5.1 et vSpher Web Clien
- vCenter 5.5
  - VM restore même sans hôte
  - offsite backup data storage

## Keeping Systems Available

VMware High Availability

Hote Failure => VM redémaré sur un autre hôte: Facile à paramètrer

HA agent => chaque hôte physqque

vSphere 5 améliore Ha par:

- utilisation de datastore partager et c'est I/O path
- pas de dépendence DNS de chaque noeud
- amélioration de la visibilité des hôtes et des maîtres/escalves

Considération pour une meilleur haute disponibilité:

- Redondé SAN component: HBA, Switches, SAN ports
- Redondé I/O paths

Suivre les étapes pour activer vSphere HA

## VMware Fault Tolerance

Faute tolérance disponible pour les applications critiques:

- pas de tolérance à la panne
- 1vCPU par VM
- modéle du CPU correctement modéliser dans l'hôte
- Hôte dans un HA ou HA/DRS cluster
- Reprise du service presque instantanné
- Vs la plupart des hardware failures
- Tous les guest OS

Disaster Recovery

1. solution => HA ou FT cluster
   1. 2 endroid différents
   2. SAN dupliquer en mirroire
   3. Investissement résonnable si le résau est sous controle
2. solution => second datacenter
   1. Copy les VMs critique
   2. Redémarre les VMs si besoin

vSphere Site Recovery Manager:

- Planning automatique: test, failover, failback
- pas d'array réplication