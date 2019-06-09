# vSphere Network Configuration

## Virtual Switches

vSwitches:

- Configuré par un admin/ créer par VMkernel
  - NICs virtuel dans VMs avec ESXi et les NICs physiue
  - Features => configurations vSwitch
- Fournit
  - VM 2 physique
  - VM 2 VM même ESX/ESXi
  - VM 2 VM différents ESX/ESXi
  - VMkernel peut accéder au réseau physique

Ports/Port Groups:

- 2 types de vSwitches: Créer un réseau virtuel
  - Standard (vSS): 
    - ESX/ESXi 2 réseau server hôte
    - Object dans un ESX/ESXi
  - Distributed (vDS)
    - Object dans un object datacenter
    - License Entreprise
- port => défini à la création
- 2 types de ports: 
  - VMkernel port = connecté: VMotin Lans, ESXi
  - Virtual machine port group: VMs 2 réseaux prod (label réseau et VLAN ID)
- uplink => connection vSwitch 2 NIC physique

Changement réseaux peut se faire avec vSwitches => connect vSwitch à plusieurs pNICs

pNICs état: Failover/ Load balancing

vNICs => matériel virtuel défini dans une VM => mac adresse spé

## Virtual Switch Properties

- Port: (Défault 120)
- Régle: Sécurité, traffic shaping, Failover et Load Balancing
- Tab d'Adaptateur réseau: définir NICs, vitesse et duplex

Régles définie: vSwitch ou aux niveau port/port group (régle de port > régle vSwitch)

Lan Virtuel:

- Création plusieurs LANs
- Améliore la sécurité
- Moins de hardware
- Meilleur performance
- ESXi => IEE 802.1q

Régle de sécurité réseaux:

1. Mode Promiscuité
2. Changement d'adresse MAc
3. Forged transmits (Transmitions Forcé ?)

Meilleur Pratique:

- Définir en premier
- au moins 2 pNICs et pSwitches => Failover backup / Load balancing
- Réseaux séparé pour le management ESXi
- VMotion et iSCSI => isolé
- Rejeté les régle de sécurité réseaux
- Utilisé les port group, VLAN tagging et traffic shaping