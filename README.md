
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
<img width="1375" height="913" alt="002-doc-environement-de-virtualisation" src="https://github.com/user-attachments/assets/58d82b40-aec1-4e4f-bb2c-020ac958150a" />
<img width="1908" height="603" alt="003-tenant-entra-ID" src="https://github.com/user-attachments/assets/bdea57e5-9623-4b52-a542-4246133691d3" />

2. Création des utilisateurs et des groupes
Création des comptes utilisateurs dans Entra ID depuis le portail et avec PowerShell / Microsoft Graph. Création de groupes de sécurité pour les licences, politiques, applications et appareils.
<img width="1609" height="562" alt="004-User-GID" src="https://github.com/user-attachments/assets/82b02b40-e94c-4d70-8d79-8835b67575b9" />
<img width="1448" height="322" alt="006-ps-creation-user" src="https://github.com/user-attachments/assets/fd01876c-58ba-4684-8e36-9c586cc22966" />
<img width="1614" height="841" alt="005-GUser" src="https://github.com/user-attachments/assets/6fba3f49-5c06-4ac5-854d-be469cebbf95" />
<img width="1448" height="824" alt="007-creation-group" src="https://github.com/user-attachments/assets/5d47e462-e1dc-4e4f-9237-8bb1ef4821de" />
<img width="1470" height="956" alt="010-ps-creation-group" src="https://github.com/user-attachments/assets/296b09dc-3663-43ab-9d51-fc4497c5dbf8" />

3. Rôles RBAC et licences
Mise en œuvre du principe du moindre privilège avec des rôles tels que Administrateur des utilisateurs et Administrateur du support technique. Attribution de licences individuellement puis à travers un groupe.
<img width="1863" height="924" alt="011-Attribution-licences" src="https://github.com/user-attachments/assets/d4a453fb-2828-494a-8d89-81a6005254b1" />
<img width="1892" height="929" alt="012-Attribution-Roles" src="https://github.com/user-attachments/assets/728fb654-0415-4ee4-b82b-1bb6219ca18d" />

4. Collaboration externe — Entra B2B
Invitation d'un utilisateur externe, validation de l'acceptation de l'invitation et configuration de la gouvernance des invités.
<img width="1527" height="798" alt="013-Invitation-B2B" src="https://github.com/user-attachments/assets/ec5e1bb8-cdae-45d9-93ff-b6fd841b5b95" />

5. Groupe dynamique basé sur les attributs
Création d'une règle d'appartenance dynamique basée sur un attribut utilisateur, puis validation de l'ajout automatique d'un membre après modification de son attribut.
<img width="1882" height="558" alt="014-Régles-group-Dynamique" src="https://github.com/user-attachments/assets/05be6f4a-67e1-491a-9ad8-c551040f2c0f" />

6. Synchronisation hybride avec Microsoft Entra Connect
Déploiement du contrôleur de domaine, installation et configuration de Microsoft Entra Connect avec synchronisation des identités et validation de la remontée des comptes vers Entra ID.
<img width="1681" height="522" alt="016-Synchro-entra-srv" src="https://github.com/user-attachments/assets/5ee9215a-c311-49cc-9f21-7d83ad59ac9d" />
<img width="1470" height="956" alt="0112222-Synchronisation-entra-srv" src="https://github.com/user-attachments/assets/543fac93-58de-41d1-93c6-2fdff7cf14e7" />


7. Jonction d'un appareil à Microsoft Entra ID
Jonction d'un poste Windows 11 à Entra ID et validation avec dsregcmd /status.
<img width="1327" height="798" alt="017-A-Jonction-Appareil-W11" src="https://github.com/user-attachments/assets/779a934f-5cf7-498c-986d-69c3755746e3" />
<img width="1283" height="489" alt="017-C-Jonction" src="https://github.com/user-attachments/assets/40b48d3d-2196-439c-82fb-faa423b35804" />
<img width="1156" height="806" alt="017-B-Jonction" src="https://github.com/user-attachments/assets/964af035-0072-464d-9e1e-c1ca9d620a39" />

8. Inscription automatique dans Microsoft Intune
Configuration de l'inscription automatique MDM. Diagnostic d'un cas où le poste était joint à Entra ID mais n'était pas géré dans Intune, puis résolution par resynchronisation manuelle du compte professionnel 
<img width="1888" height="880" alt="018-B-intune" src="https://github.com/user-attachments/assets/ae5186fe-46b5-482b-92b4-554fe9ce699d" />
<img width="1860" height="549" alt="018-Inscription-intune" src="https://github.com/user-attachments/assets/f41e1c42-58aa-4f1a-8f2c-1074383c2671" />

10. Profil de configuration d'appareil
Création et attribution d'un profil de restriction d'appareil ciblé par groupe de sécurité, avec validation avant/après
sur le poste.

11. MFA via l'accès conditionnel
Création d'une politique Conditional Access exigeant la MFA pour l'accès à Microsoft 365 et validation du parcours
utilisateur.
12. Réinitialisation de mot de passe en libre-service — SSPR
Configuration de Self-Service Password Reset, activation des méthodes d'authentification et test du parcours de
réinitialisation.
13. Politique de conformité des appareils
Définition de critères de conformité tels que la version minimale de Windows et la présence de Microsoft Defender
Antivirus, puis liaison avec Conditional Access
14. Chiffrement BitLocker géré par Intune
Déploiement d'une politique BitLocker avec sauvegarde de la clé de récupération dans Entra ID et validation du
chiffrement.
15. Déploiement d'une application Microsoft 365
Configuration et déploiement obligatoire de Microsoft 365 Apps en 64 bits avec suivi jusqu'au succès.
16. Déploiement Windows Autopilot
Collecte du Hardware ID avec Get-WindowsAutoPilotInfo.ps1, enregistrement du matériel, création du profil de
déploiement piloté par l'utilisateur et validation du scénario complet jusqu'au bureau Windows.
17. Microsoft Defender for Endpoint
Déploiement de stratégies de sécurité et d'antivirus via Intune et comparaison de Windows Security entre un poste
géré et un poste non géré.
18. Group Policy Analytics
Export d'une GPO depuis Active Directory, analyse avec Group Policy Analytics et identification des paramètres
pouvant être migrés vers une gestion moderne Intune.

Compétences démontrées

• Administration de Microsoft Entra ID et Microsoft Intune
• Gestion des utilisateurs, groupes, groupes dynamiques, licences et rôles RBAC
• Gestion des identités cloud et hybrides avec Microsoft Entra Connect
• Entra ID Join et Intune MDM Enrollment
• Windows Autopilot et déploiement automatisé des postes
• Gestion des applications et politiques de configuration
• Conditional Access, MFA et SSPR
• Politiques de conformité et contrôle des accès
• BitLocker et Microsoft Defender
• Mobile Application Management (MAM)
• PowerShell et Microsoft Graph
• Group Policy Analytics et transition GPO → Intune
• Diagnostic des problèmes d'inscription MDM et de synchronisation
• Mise en oeuvre de principes Zero Trust

Défi technique rencontré

L'un des principaux défis rencontrés durant le laboratoire concernait l'inscription automatique d'un poste Windows
dans Microsoft Intune.
Le poste était correctement joint à Microsoft Entra ID, ce qui pouvait être vérifié avec dsregcmd /status. Cependant,
l'appareil n'apparaissait pas immédiatement comme appareil géré dans Intune.
L'analyse a permis d'identifier un problème lié à l'ordre de configuration de l'inscription automatique MDM : la
jonction de l'appareil avait eu lieu avant que la configuration de l'inscription automatique soit correctement
appliquée.
La résolution a nécessité une resynchronisation manuelle du compte professionnel sur le poste afin de relancer le
processus d'inscription.
Cette expérience m'a permis de comprendre l'importance de vérifier méthodiquement les dépendances entre les
services et d'utiliser dsregcmd /status comme outil de diagnostic avant de me fier uniquement à l'interface
graphique.

Ce que j'ai appris

Ce projet m'a permis de comprendre que la gestion moderne des terminaux repose sur l'intégration de plusieurs
composants : identité, inscription, configuration, sécurité, applications, déploiement, conformité et administration.
J'ai également développé une meilleure compréhension de la différence entre une administration traditionnelle
basée sur Active Directory et GPO et une gestion moderne basée sur Entra ID, Intune, Conditional Access, Autopilot
et Defender.
Le laboratoire m'a permis de mettre en pratique une approche de sécurité basée sur le principe Zero Trust en
combinant identité, MFA, conformité des appareils et politiques d'accès conditionnel.

Conclusion

Ce projet m'a permis de mettre en pratique les principaux concepts de la gestion moderne des terminaux Microsoft
dans le cadre de ma préparation à la certification MD-102.
L'environnement couvre l'ensemble du cycle de gestion moderne : Identité - Inscription - Configuration - Sécurité - Applications - Déploiement - Conformité - Administration.
Les différents scénarios réalisés m'ont permis de développer des compétences pratiques en Microsoft Entra ID, Microsoft Intune, Windows Autopilot, Microsoft Entra Connect, Conditional Access, BitLocker, Microsoft Defender, PowerShell et Microsoft Graph.
Le projet m'a également permis de développer une approche de dépannage basée sur l'analyse des dépendances entre les différents services plutôt que sur la simple configuration des interfaces graphiques
