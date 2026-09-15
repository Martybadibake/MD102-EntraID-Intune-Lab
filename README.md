Déploiement d'une infrastructure de gestion moderne des terminaux
(Microsoft Entra ID / Microsoft Intune)

Projet réalisé en environnement de laboratoire personnel — préparation à la certification Microsoft MD-102

Contexte et objectif

Ce projet consiste en la mise en place complète d'une infrastructure de gestion moderne des terminaux basée sur Microsoft Entra ID et Microsoft Intune, en environnement de laboratoire, reproduisant les conditions d'un déploiement d'entreprise réel : de la préparation de l'identité (locale et cloud) jusqu'au déploiement automatisé de postes Windows via Windows Autopilot, en passant par la sécurisation des accès et des données.

L'objectif était de maîtriser l'écosystème central de la gestion de parc informatique moderne en entreprise , celui qui remplace progressivement les infrastructures Active Directory / GPO traditionnelles  utilisé pour automatiser l'inscription des appareils, appliquer des politiques de sécurité, déployer des applications et garantir la conformité d'un parc hétérogène (Windows, iOS, Android).

Technologies et outils utilisés

•	Microsoft Entra ID (identités, groupes, rôles RBAC, accès conditionnel)
•	Microsoft Intune (centre d'administration, gestion des appareils et des applications)
•	Windows Server (Active Directory Domain Services, DNS)
•	Microsoft Entra Connect (synchronisation d'identité hybride)
•	Windows 11/10 (poste client) et Windows Autopilot (déploiement moderne)
•	Microsoft Defender for Endpoint et BitLocker (sécurité des terminaux)
•	PowerShell et Microsoft Graph (automatisation et administration en ligne de commande)
•	VMware Fusion / Hyper-V (virtualisation du laboratoire)

Étapes clés de la réalisation

Étapes clés de la réalisation
1.	Préparation de l'infrastructure de laboratoire Création d'un tenant Microsoft 365 Developer (Entra ID + Intune) et déploiement d'une machine virtuelle Windows 11 comme poste client de test.
2.	Création d'utilisateurs et de groupes Création d'utilisateurs via le portail Microsoft Entra et en ligne de commande avec PowerShell / Microsoft Graph (New-MgUser), et création d'un groupe de sécurité avec appartenance affectée.
3.	Rôles RBAC et licences Attribution de rôles d'administration délégués (Administrateur des utilisateurs, Administrateur de support technique) et attribution de licences Microsoft 365 à un utilisateur puis à un groupe entier.
4.	Collaboration externe (Entra B2B) Invitation d'un collaborateur externe, validation de l'acceptation de l'invitation, et configuration de la gouvernance des invités (restriction des droits d'invitation aux rôles d'administrateur).
5.	Groupe dynamique basé sur des attributs Création d'une règle d'appartenance dynamique basée sur un attribut utilisateur (ex. : département) et validation de l'ajout automatique d'un membre après modification de son attribut.
6.	Synchronisation hybride avec Microsoft Entra Connect Déploiement d'un contrôleur de domaine Active Directory, installation et configuration de Microsoft Entra Connect (synchronisation de hachage de mot de passe), et validation de la synchronisation des comptes vers Entra ID.
7.	Jonction d'un appareil à Microsoft Entra ID Jonction d'un poste Windows à Entra ID via Accès professionnel ou scolaire, et validation de la jonction via la commande dsregcmd /status.
8.	Inscription automatique dans Microsoft Intune Configuration de l'étendue de l'utilisateur MDM et diagnostic d'un cas réel de blocage d'inscription (appareil joint avant l'activation du paramètre), résolu par resynchronisation manuelle.
9.	Profil de configuration d'appareil Création et attribution d'un profil de restriction d'appareil (blocage de jeux, exclusions Microsoft Defender) ciblé via un groupe de sécurité, avec validation avant/après sur le poste.
10.	MFA via l'accès conditionnel Création d'une politique d'accès conditionnel exigeant l'authentification multifacteur pour l'accès à Office 365, avec validation complète du parcours utilisateur.
11.	Réinitialisation de mot de passe en libre-service (SSPR) Activation des méthodes d'authentification (courriel, SMS, questions de sécurité) et test du parcours de réinitialisation de mot de passe côté utilisateur.
12.	Politique de conformité des appareils Définition de critères de conformité (version minimale du système d'exploitation, Microsoft Defender Antivirus requis) et liaison avec une politique d'accès conditionnel bloquant les appareils non conformes.
13.	Chiffrement BitLocker géré par Intune Déploiement d'une stratégie de chiffrement de disque avec sauvegarde automatique de la clé de récupération dans Entra ID, et validation du chiffrement actif sur le poste cible.
14.	Déploiement d'une application Microsoft 365 Configuration et déploiement obligatoire de Microsoft 365 Apps (architecture 64 bits, canal de mise à jour entreprise) avec suivi du rapport d'installation jusqu'à confirmation de succès.
15.	Déploiement Windows Autopilot Collecte du Hardware ID via PowerShell (Get-WindowsAutoPilotInfo), création d'un profil de déploiement piloté par l'utilisateur, et validation du scénario complet de bout en bout jusqu'au bureau Windows.
16.	Politique de protection des applications mobiles (MAM) Configuration d'une politique de protection Outlook empêchant le copier-coller de données professionnelles vers des applications personnelles, testée sur un appareil mobile.
17.	Microsoft Defender for Endpoint Déploiement de stratégies d'expérience de sécurité Windows et d'antivirus via Intune, avec comparaison directe de l'interface Windows Security entre un poste géré et un poste non géré.
18.	Group Policy Analytics Export d'une stratégie de groupe (GPO) locale depuis un contrôleur de domaine, analyse du taux de compatibilité avec la gestion moderne dans Intune, et production d'un rapport de préparation à la migration.
Compétences démontrées
•	Conception et déploiement d'une infrastructure d'identité hybride (Entra ID + Active Directory)
•	Administration d'un outil de gestion de parc informatique à l'échelle entreprise (Microsoft Intune)
•	Automatisation du déploiement de postes via Windows Autopilot
•	Résolution de problématiques d'inscription MDM et de synchronisation d'identité
•	Mise en œuvre d'une architecture de sécurité Zero Trust (accès conditionnel, conformité, MFA)
•	Compréhension des scénarios de transition GPO → gestion moderne







