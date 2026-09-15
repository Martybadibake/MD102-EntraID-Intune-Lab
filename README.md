Déploiement d'une infrastructure de gestion moderne des terminaux

Microsoft Entra ID / Microsoft Intune

Projet réalisé en environnement de laboratoire personnel — préparation à la certification Microsoft MD-102

Contexte et objectif
Ce projet consiste en la mise en place d'une infrastructure moderne de gestion des terminaux basée sur Microsoft Entra ID et Microsoft Intune, dans un environnement de laboratoire personnel reproduisant les principaux scénarios rencontrés dans une infrastructure d'entreprise.

L'objectif était de maîtriser le cycle complet de gestion moderne des terminaux, depuis la gestion des identités et des groupes jusqu'à l'inscription, la configuration, la sécurisation et le déploiement automatisé des postes Windows.

Le projet couvre notamment la gestion des identités avec Microsoft Entra ID, l'administration des appareils avec Microsoft Intune, la synchronisation hybride avec Active Directory, la gestion des applications, les politiques de conformité, l'authentification multifacteur, l'accès conditionnel, BitLocker, Microsoft Defender, Windows Autopilot, la protection des applications mobiles et l'analyse des stratégies GPO.

Architecture du laboratoire
L'environnement a été conçu afin de reproduire une architecture hybride combinant une infrastructure locale Windows et les services Microsoft Cloud.
Technologies et outils utilisés
Technologie	Utilisation
Microsoft Entra ID - Identités, groupes, rôles RBAC et accès conditionnel
Microsoft Intune - Gestion des appareils, applications, conformité et sécurité
Microsoft Entra Connect	Synchronisation Active Directory / Entra ID
Active Directory Domain Services - Gestion des identités locales
DNS	Résolution de noms de l'environnement local
Windows 11	Poste client de laboratoire
Windows Autopilot	Déploiement moderne des postes
Microsoft Defender	Protection des terminaux
BitLocker	Chiffrement des disques
Microsoft 365	Services et applications cloud
PowerShell	Administration et automatisation

1. Préparation de l'infrastructure de laboratoire
Création et préparation du laboratoire : tenant Microsoft 365, Entra ID, Intune, utilisateurs, groupes, licences, infrastructure locale Windows, Active Directory, DNS, poste Windows 11 et virtualisation

2. Création des utilisateurs et des groupes
Création des comptes utilisateurs dans Entra ID depuis le portail et avec PowerShell / Microsoft Graph. Création de groupes de sécurité pour les licences, politiques, applications et appareils.
3. Rôles RBAC et licences
Mise en œuvre du principe du moindre privilège avec des rôles tels que Administrateur des utilisateurs et Administrateur du support technique. Attribution de licences individuellement puis à travers un groupe.
4. Collaboration externe — Entra B2B
Invitation d'un utilisateur externe, validation de l'acceptation de l'invitation et configuration de la gouvernance des invités.
5. Groupe dynamique basé sur les attributs
Création d'une règle d'appartenance dynamique basée sur un attribut utilisateur, puis validation de l'ajout automatique d'un membre après modification de son attribut.
6. Synchronisation hybride avec Microsoft Entra Connect
Déploiement du contrôleur de domaine, installation et configuration de Microsoft Entra Connect avec synchronisation des identités et validation de la remontée des comptes vers Entra ID.


Microsoft Graph	Administration programmatique d'Entra ID
VMware Fusion / Hyper-V	Virtualisation de l'environnement de laboratoire
