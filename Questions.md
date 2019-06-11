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

## VMFS Virtual Machine File System (VMFS)

système de fichiers en cluster de VMware. Il a été développé pour stocker des images de disque de machine virtuelle, y compris des instantanés.

## pool de ressource

Un pool de ressource Vmware est un agrégat des ressources physiques des hôtes en termes de cpu et de mémoire qui peuvent être alloués aux machines virtuelles hébergées dessus. Plutôt qu’une machine ne puise utiliser que les ressources de son hôte, elle pourra utiliser toutes les ressources du pool de ressources d’hôtes mises à disposition. Cela permet également de répartir la charge et d’équilibrer l’utilisation des ressources des hôtes en plus de pouvoir définir des priorités/seuil pour chaque machines virtuelles et utilisateurs.

Ces pools de ressources peuvent apporter les avantages suivants :

-Isolation de performance : Permet d’empêcher les machines virtuelles de monopoliser les ressources d’un hôte.

-Utilisation efficace : Permet d’utiliser au mieux les ressources disponible d’un hôte, par exemple si un hôte du pool de ressource à une charge moins élevée, il va prendre automatiquement en charge les prochaines actions à effectuer.

3 Attribues primaires:

- Shares: montant moyen qu'un objet à d'une resource
- Reservation: min somme de resources
- Limits: max

## desktop virtualization / server virtualization

## vm kernel

VMkernel est un système d'exploitation de type POSIX développé par VMware. 

Le VMkernel est la liaison entre les machines virtuelles (VM) et le matériel physique qui les prend en charge.  

## 3 techniques de virtu

- Emulation
- Para-virtualisation
- Full virtualisation

## templates

Un modèle est une copie maîtresse d'une machine virtuelle qui peut être utilisée pour créer de nombreux clones.

Si vous créez une machine virtuelle que vous souhaitez cloner fréquemment, définissez cette machine comme un modèle. Un modèle est une copie maîtresse d'une machine virtuelle pouvant être utilisée pour créer et mettre en service des machines virtuelles. Les modèles ne peuvent pas être activés ou modifiés, et sont plus difficiles à modifier que les machines virtuelles ordinaires. Un modèle offre un moyen plus sécurisé de conserver une configuration de machine virtuelle que vous souhaitez déployer plusieurs fois.

Lorsque vous clonez une machine virtuelle ou déployez une machine virtuelle à partir d'un modèle, la machine virtuelle clonée résultante est indépendante de la machine virtuelle ou du modèle d'origine. Les modifications apportées à la machine virtuelle ou au modèle d'origine ne sont pas répercutées dans la machine virtuelle clonée et les modifications apportées à la machine virtuelle clonée ne sont pas répercutées dans la machine virtuelle ou le modèle d'origine.

## CLI

Installation sur le VCenter

La commande d'interface de ligne de commande vSphere (vSphere CLI) jeu vous permet d'exécuter l'administration du système commun des commandes contre les systèmes ESXi de toute machine avec un accès réseau à ces systèmes. Vous pouvez également exécuter la plupart des commandes vSphere CLI contre un système vCenter Server et cibler tout système ESXi ce système vCenter Server gère. vSphere CLI comprend également un ensemble de commandes de gestion hôte: le jeu de commandes, les commandes esxcli vicfg-, et d'autres commandes. vSphere CLI comprend également les commandes DCLI, qui vous permettent de gérer des services dans l'API vSphere REST et sont présentés par les interfaces SDK d'automatisation vSphere.

## VMware Tools

VMware Tools est une suite d'utilitaires que vous installez dans le système d'exploitation d'une machine virtuelle.

VMware Tools améliore les performances d'une machine virtuelle et permet d'utiliser un grand nombre de ses fonctions d'utilisation simples dans les produits VMware.

Bien qu'un système d'exploitation invité puisse fonctionner sans VMware Tools, de nombreuses fonctionnalités VMware ne sont disponibles qu'après l'installation de VMware Tools. Par exemple, si vous n'avez pas installé VMware Tools sur la machine virtuelle, vous ne pouvez pas obtenir les informations de signaux de pulsation fournies par les systèmes d'exploitation invités ou vous ne pouvez pas non plus utiliser les options d'arrêt ou de redémarrage à partir de la barre d'outils. Vous pouvez uniquement utiliser les options d'alimentation et vous devez arrêter vos systèmes d'exploitation invités à partir de chaque console de machine virtuelle. Vous ne pouvez pas utiliser VMware Tools pour connecter et déconnecter les périphériques virtuels ni pour réduire les disques virtuels.

## VMware VCenter Server

VMware **vCenter** Server est un logiciel de gestion de serveurs avancée qui vous offre une plate-forme centralisée pour le contrôle de vos environnements VMware vSphere et vous permet d'automatiser et fournir une infrastructure virtuelle dans l'ensemble du Cloud hybride en toute confiance.

## VSphere

VMware **vSphere** est un logiciel d'infrastructure de Cloud computing de l'éditeur VMware, c'est un hyperviseur de type 1 (Bare Metal), basé sur l'architecture VMware ESXi.

VMware vSphere est le nom de marque de la famille de produits de virtualisation de VMware.

## distributed power management

option de VMware Distributed Resource Scheduler (DRS)

La consolidation des serveurs physiques en machines virtuelles qui partagent elles hébergent des ressources physiques peuvent entraîner des réductions importantes des coûts liés à l'entretien du matériel et la consommation d'énergie. VMware Distributed Power Management (VMware DPM) permet des économies d'énergie supplémentaires au-delà de cet avantage initial en consolidant de manière dynamique les charges de travail encore plus pendant les périodes de faible utilisation des ressources. Les machines virtuelles sont migrés sur moins d'hôtes et les hôtes ESX non nécessaires sont mis hors tension

## 3 méthodes d'installation de esxi

- USB
- CD
- PXE (réseau)

## pourquoi avoir plusieur interface sur un vswitches

Que faut il pour un DRS ?

- Cluster + vMotion
- Storage en mode Kernel

## Bonnes pratiques installations ESXi

- Identifié le réseau à managé and le NIC
- Etablire un plan de synchronisation du temps
- Sécurité de la console
- Droit accès au DCUI
- Aucun LUNs sur l'hôte
- ESXi Lockdown mode

Tâches après installation:

- Synchronisation du temps
- Paramétrage du DNS et du réseau

## Silicon Base

![img](https://www.supinfo.com/articles/resources/206638/1760/0.png)

#### La virtualisation complète :

C’est la première génération de la virtualisation pour les serveurs x86/x64. Avec cette technique, tous le matériel est émulé, même le CPU. Le système d’exploitation invité n’a pas conscience d’être virtualisé. Les avantages de cette solution sont l’isolation des VM de l’OS hôte, le contrôle de l’accès aux ressources des VM et la portabilité des VM. Cependant, les performances sont limitées à cause de la virtualisation du matériel.

#### La paravirtualization :

La paravirtualisation permet aux hyperviseurs d'être plus simples et aux machines virtuelles fonctionnant dessus d'atteindre un niveau de performance proche du matériel réel. Cependant, les systèmes d'exploitation doivent explicitement être modifiés afin de fonctionner sur ces hyperviseurs.

#### La virtualisation assistée par matériel :

La virtualisation assistée par matériel est une technique de virtualisation qui permet la virtualisation complète et efficace en utilisant les capacités matérielles, principalement celles des processeurs de l’hôte. La virtualisation complète est utilisée pour simuler un environnement complet de matériel, ou d'une machine virtuelle, dans lequel un système d'exploitation invité non modifié exécute dans un isolement complet. La virtualisation assistée par matériel est présente dans les processeurs x86 (Intel VT- x ou AMD – V).

## vSphere Data Protection

- vSphere Data Protection est une solution de sauvegarde et de récupération conçue pour les environnements vSphere.

VMware Data Protection:

- remplace VMware Data Recovery
- basé sur EMC's Avamar
- vCenter 5.1 et vSpher Web Clien
- vCenter 5.5
  - VM restore même sans hôte
  - offsite backup data storage

## Converter Standalone

Convertit rapidement des machines physiques locales et distantes en machines virtuelles sans aucune interruption de service. La possibilité d’effectuer plusieurs conversions simultanées autorise les mises en œuvre de virtualisation à grande échelle.

## Full-Virtualisation



## 2 types de connections network ports

- port group : 
- vmkernel port : 

## Donnez 4 fichiers d'une vm ?

.nvram
.vmdk
.vmsd
.vmx
.vmxf

## Comment les host-vsphere sont licencié et leurs niveaux de licence :  Rep : en fonction du processueurs, niveaux de licences : standard, entreprises, essentials



## qu'est ce que le thick provisioning et quels sont les deux types de thick provisioning



## Cite 3 avantages de classer les vms dans un repertoire



## qu'est ce que le Vmsso et ou est ce que les credentials sont stockés



