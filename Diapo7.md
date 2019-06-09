# Security in a vSphere 5 Environment

## Overview

Problème de sécurité dans:

- Sécurité de l'hôte
- Réseau virtuel
- VM
- Os guest
- objet dans vCenter Server

Access Elements:

- Controler par:
  - Utilisateur et Groupe
    - créer comme utilisateur Linux: utilisation d'un AD
    - utilisateurs en accès direct => vSphere Client
    - Authentifier par SSO
    - Voyent les instances vCenter autorisé
    - =/= status created dans vCenter
  - Role
  - Privilége
  - Permissions

## Setting up Security

Permissions = utilisateur + role assigner + sur l'objet

Membres: Windows Administrators = Administrator role

Suivre la procédure pour créer un role

Access Rules:

- Controle les usages
- effet immédiat
- se propoge mais peut être overrider

Les rôles sont cumulatif

Les permissions spécifiques > spé général

Permissions utilisateur > all

Access rules peuvent être défini dans de multiples endroid