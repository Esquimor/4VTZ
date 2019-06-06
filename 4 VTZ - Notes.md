# 4 VTZ - Notes

## Introduction to Virtualization ans vSphere

### Introduction to Virtualization

Matériels:

- Manque de Fléxibilité
- Une tâche

Applications:

- Task-specific
- Os contrôle le matériel

### Application Domains

Virtualisation du stockage:

- Fléxible
- N'importe quel matériel
- Optimisation de l'espace

Application virtualisation:

- Isolation des applications
- Streaming d'applications

Virtualisation du Desktop:

- Desktop simulé à travers le réseau

Virtualisation du réseau

### Why Moving to Virtualization

Réduction Capex (Capital) /Opex (Humain)

Server, Espace, éléctricité, sécurité...

### The virtualization market

VMware, Citrix/Xen, Microsoft/HyperV, Virtuozzo/Parralels, KVM, OracleVm/VirtualBox

### VMware's virtualization solution

Groupe de produits:

- Desktop: plusieurs Vm, quick redeploy, simulate networks, testing... / VMware Workstation, Player, Server, Fusion
- Datacenter (serveur): 
- Cloud: Datacenter physique en un seul composant

Desktop et Datacenter sont très différent

vSphere 5:

1. ESXi Host: Virtualisation, Abstraction, Management des ressources de l'hôte
2. vCenter Server: Centralise le management des applications
3. vSphere Cliet: UI graphique
4. vSphere Web Client
5. vSphere SMP: 1 VM => plusieurs virtual processors
6. vSphere Virtual Machine File System (VMFS)
7. vSphere Distributed Resource Scheduler (DRS)
8. vSphere Storage DRS
9. VMoton
10. Storage VMotion
11. vSphere HA
12. vSphere Fault Tolerance: Two Vm dans 2 ESXi
13. VMware Update Manager



Datacenter:

- vSphere: virtualise IT infrastructure
- Resources virtuel:
  - Aggreger
  - Provisioner Dynamiquement
  - Managé par vCenter
- ESXi Hosts

Connexion to vSphere Client

- Directement hôte ESX/ESXi
- Indirectement avec vCenter Server



## Installing vSphere 5 Components

### ESXI Host Installation

ESXi Host:

- Couche de virtualisation
- Regroupement par clusters contre panne et management des resouces
- Installer sur le disk dur

Composant Clef:

- VMkernel: management des ressources physiques
- Commence avec vSphere 5.0

Existe: Ligne de Commande Alternatif pour ESXi

Pour ESXI: existent des requirements minimum => Vérification avec VMware Compatibility Guide

Installation:

1. CD/DVD disk
2. USB flash drive
3. PXE: réseau

Méthodes d'installations:

1. Interactive
2. Scripter
3. Auto deploy

Suivre la documentation pour les étapes d'installations

### ESXI Host Configurations

Meilleurs Pratiques:

- Identifié le réseau à managé and le NIC
- Etablire un plan de synchronisation du temps
- Sécurité de la console
- Droit accès au DCUI
- Aucun LUNs sur l'hôte
- ESXi Lockdown mode

Tâches après installation:

- Synchronisation du temps
- Paramétrage du DNS et du réseau

Host Profiles: Gestions plus facile de l'ESXi hosts

### Enhancing host performance

- Utiliser les disques physiques
- Assez de mémoires
- NICs management mémoire séparer
- Processors le plus rapide

### VCenter Server

Point central de l'administration de l'infrastructure: Service sur Windows/Windows Server

##### vCenter Server DB: Composant major => vCenter Database

- Maintien les status de l'infrastructure
- Configurer à l'installation de vCenter
- Local/Remote

##### SSO (Single Sign On)

Possibilité de faire du SSO => utilise Windows ADDS

1. Loger avec name/password
2. Passe par SSO
3. SSO valide => token
4. Token d'identification pour les services



vCenter demande une liste de prérequis pour son installation

Phase majeur d'installation:

1. Installer vCenter Server
2. Ajout vCenter Database créer précédement
3. vCenter login
4. Installation par défault Oui/non
5. 1 vCenter ou group
6. Choix du port
7. Install
8. Finish

Après installation faire les configurations nécessaires

### VSphere Licensing

- Clef License
- Sur les per-processor => illimité cores par processor



## vSphere 5 Features, vSphere Web Client and P2V

### New Features of vSphere 5.5

Changement Majeur:

- SSO:  (5.1, améliorer 5.5)

- vSphere Web Client: administration par page web

- ESXi

  - Rechargement à chaud SSD
  - Réduction: CPU besoin

- Virtual Machine Changes

  - Meilleur rendue 3d / graphique
  - Nouveau format VM

- ### vCenter: + hôtes et vm supporté

- vSphere HA: travail conjointement VM monitoring

- vSphere Data Protection: \+ de sécurité

- vSphere Storage: \+ de stockage disponible

- Réseaux: \+ bande passante et filtres du traffic

### VSphere Web Client

vSphere client => nouvelle interface = support complet des opérations

Se reporter au Cours pour les images

### P2V Tools

Simulation d'une machine physique avec la virtualisation

S'assurer du réseau et de la connectivité avant de faire la conversion

Besoin d'un logiciel:

- Native produit VMware
- Application tiers

## vSphere Network Configuration

### Virtual Switches

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

### Virtual Switch Properties

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



