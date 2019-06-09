# Installing vSphere 5 Components

## ESXI Host Installation

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

## ESXI Host Configurations

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

## Enhancing host performance

- Utiliser les disques physiques
- Assez de mémoires
- NICs management mémoire séparer
- Processors le plus rapide

## VCenter Server

Point central de l'administration de l'infrastructure: Service sur Windows/Windows Server

vCenter Server DB: Composant major => vCenter Database

- Maintien les status de l'infrastructure
- Configurer à l'installation de vCenter
- Local/Remote

 SSO (Single Sign On)

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

## VSphere Licensing

- Clef License
- Sur les per-processor => illimité cores par processor