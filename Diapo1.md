# Introduction to Virtualization ans vSphere

## Introduction to Virtualization

Matériels:

- Manque de Fléxibilité
- Une tâche

Applications:

- Task-specific
- Os contrôle le matériel

## Application Domains

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

## Why Moving to Virtualization

Réduction Capex (Capital) /Opex (Humain)

Server, Espace, éléctricité, sécurité...

## The virtualization market

VMware, Citrix/Xen, Microsoft/HyperV, Virtuozzo/Parralels, KVM, OracleVm/VirtualBox

## VMware's virtualization solution

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