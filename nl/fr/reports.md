---

copyright:
  years: 2017
lastupdated: "2017-08-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# Détails des rapports par type

## Connexions via le pare-feu
{: #firewalllogins}

Rend compte des événements de connexion d'administrateur aux unités pare-feu Vyatta.

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>Nom de l’événement</dt>
<dd>Type d'événement (Echec de la connexion SSH par l'utilisateur - mot de passe incorrect, Echec de l'authentification, Session fermée, Mot de passe accepté pour l'utilisateur, Session ouverte par l'utilisateur).</dd>
<dt>Catégorie de bas niveau</dt>
<dd>Détails de l'événement (Echec de la connexion SSH, Session fermée, Réussite de la connexion à l'hôte, Session ouverte).</dd>
<dt>Nom d'utilisateur</dt> 
<dd>Données d'identification (nom utilisateur) de l'utilisateur ayant lancé la session.</dd>
<dt>IP source</dt>
<dd>Adresse IP depuis laquelle l'utilisateur lance la session.</dd>
<dt>IP de destination</dt>
<dd>Cible de la session.</dd>
<dt>Source de journal</dt>
<dd>Source de l'événement (nom d'hôte du pare-feu qui a généré l'événement).</dd>
</dl>

## Refus du pare-feu
{: #firewalldenies}

Rend compte des événements générés par les unités pare-feu Vyatta lors du rejet d'une demande d'accès en raison des règles de pare-feu en vigueur.
  
### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date et heure auxquelles l'événement s'est produit.</dd>
<dt>Nom de l’événement</dt>
<dd>Type d'événement (Echec de la connexion SSH par l'utilisateur - mot de passe incorrect, Echec de l'authentification, Session fermée, Mot de passe accepté pour l'utilisateur, Session ouverte par l'utilisateur).</dd>
<dt>Catégorie de bas niveau</dt>
<dd>Détails de l'événement de refus par le pare-feu</dd>
<dt>IP source</dt> 
<dd>Adresse IP source depuis laquelle la connexion réseau et/ou l'attaque émane.</dd>
<dt>Port source</dt>
<dd>Port de destination du protocole.
<dt>IP de destination</dt>
<dd>Cible de la session.</dd>
<dt>Port de destination</dt>
<dd>Port de destination du protocole.</dd>
<dt>Protocole</dt>
<dd>Protocole de communication (tcp/udp).</dd>
<dt>Source de journal</dt>
<dd>Source de l'événement (nom d'hôte du pare-feu qui a généré l'événement).</dd>
<dt>Nombre d'événements</dt>
<dd>Nombre d'événements de ce type.</dd>
</dl>

## Connexions au système d'exploitation
{: #oslogin}

Rend compte des événements générés par le système d'exploitation lorsqu'un administrateur ouvre une session SSH sur un système Bluemix.

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>Nom de l’événement</dt>
<dd>Type de l'événement (authentification de l'espace utilisateur, échec de l'authentification de l'espace utilisateur)</dd>
<dt>Nom d'utilisateur</dt> 
<dd>Nom d'utilisateur de l'utilisateur ayant lancé la procédure d'authentification.</dd>
<dt>Adresse source</dt>
<dd>Adresse IP depuis laquelle l'utilisateur lance la session.</dd>
<dt>IP de destination</dt>
<dd>Cible de la session.</dd>
<dt>Source de journal</dt>
<dd>Source de l'événement (nom d'hôte du serveur depuis lequel l'événement a été généré).</dd>
</dl>

## Connexions au serveur de connexion 
{: #loginserverlogins}

Rend compte des événements générés par le composant de connexion de la plateforme Bluemix lorsqu'un utilisateur de cette plateforme lance une session depuis la ligne de commande, les API REST ou la console Bluemix.

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>Nom de l’événement</dt>
<dd>Type de l'événement (Authentification de l'espace utilisateur, Echec de l'authentification de l'espace utilisateur)</dd>
<dt>Utilisateur</dt> 
<dd>ID de l'utilisateur ayant lancé la procédure d'authentification.</dd>
<dt>Composant_plateforme_Bluemix</dt>
<dd>Composant ayant généré l'événement (serveur_de_connexion).</dd>
<dt>Type du message</dt>
<dd>Type de l'opération (connexion, déconnexion).</dd>
<dt>Statut</dt>
<dd>Résultat de l'opération (réussite/échec).</dd>
<dt>Source de journal</dt>
<dd>Source de l'événement.</dd>
</dl>

## Administration de la base de données
{: #dbadmin}

Rend compte des événements associés aux opérations effectuées par un administrateur de base de données sur les bases de données Bluemix internes.

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>Event_Type</dt>
<dd>Type d'événement (SECURITY_RUNTIME).
<dt>Utilisateur</dt> 
<dd>Nom de l'utilisateur qui a effectué l'opération. Les utilisateurs suivants sont ceux définis dans la base de données.
<ul>
<li>UAADB: vcap, root, backup_user.
<li>CCDB: vcap, ccadmin, backup_user.
<li>Une utilisation par un autre utilisateur nécessitera d'examiner qui a réalisé l'opération. Ce contrôle peut être effectué depuis le rapport de sécurité de l'administration du système d'exploitation ou depuis le rapport de sécurité de connexion au système d'exploitation.
</ul>
</dd>
<dt>Source</dt> 
<dd>Adresse IP depuis laquelle l'utilisateur lance la commande. Les valeurs attendues sont les suivantes :
<ul>
<li>UAADB – machines virtuelles uaa et machine virtuelle nfs_WAL_server.
<li>CCDB – api_worker, clock_global,cloud_controller_ng et machines virtuelles nsf_WAL_server.
</ul>
</dd>
<dt>DB_Statement</dt>
<dd>Type d'opération (toutes les instructions de définition de données, telles que CREATE, ALTER et DROP, plus instructions de modification de données, comme INSERT, UPDATE, DELETE, TRUNCATE et COPY FROM)</dd>
<dt>DB_Name</dt>
<dd>Nom de la base de données où l'opération a été effectuée</dd>
</dl>

## Gestion des utilisateurs de la console d'administration
{: #acusermgmt}

Rend compte des activités de gestion des utilisateurs sur la console d'administration Bluemix.

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>Event_Type</dt>
<dd>Type d'événement (SECURITY_RUNTIME).
<ul>
<li>SECURITY_MGMT_REGISTRY : Add User [user ID]
<li>SECURITY_MGMT_REGISTRY : Delete User [user ID]
<li>SECURITY_AUTHN_CREDS_MODIFY : Add permission [permissions] to users [user ID].
<li>SECURITY_AUTHN_CREDS_MODIFY : Remove permission [permissions] from users [user ID].
<li>SECURITY_MGMT_CONFIG : Create organization [name].
<li>SECURITY_MGMT_CONFIG : Change organization managers, [ids].
<li>SECURITY_MGMT_CONFIG : Rename organization id [id] to new name [name].
<li>SECURITY_MGMT_CONFIG : Delete organization id [id].
<li>SECURITY_MGMT_CONFIG : Update quota for organization [id] to quota [quotaPlan].
</ul>
</dd>
<dt>Utilisateur</dt> 
<dd>Utilisateur qui a lancé l'opération (ID LDAP).
<dt>Message</dt> 
<dd>La commande a été exécutée.
<ul>
<li>Add User [ID utilisateur] - Ajoute l'utilisateur avec l'ID spécifié.
<li>Delete User [ID utilisateur] - Supprime l'utilisateur avec l'ID spécifié.
<li>Add permission [permissions] to users [ID utilisateur] - Ajoute des permissions aux utilisateurs spécifiés. Ces permissions peuvent inclure : ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read et ops.user.write.
<li>Remove permission [permissions] from users [ID utilisateur] - Retire les permissions des utilisateurs spécifiés. Les permissions peuvent inclure : ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read et ops.users.write.
<li>Create organization [nom] - Crée une organisation sous le nom spécifié.
<li>Change organization managers [ID] - Configure les utilisateurs spécifiés comme responsables d'une organisation.
<li>Rename organization id [ID] to new name [nom] - Renomme l'organisation spécifiée.
<li>Delete User [ID utilisateur] - Supprime l'utilisateur avec l'ID spécifié.
<li>Delete organization id [ID] - Supprime l'organisation spécifiée.
<li>Update quota for organization [ID] to quota [quotaPlan] - Met à jour le quota de plan pour l'organisation spécifiée. Les plans peuvent octroyer les quotas suivants : q2GB, q4GB, q8GB, q16GB, q32GB, q64GB, q128GB, q256GB, q512GB.
</ul>
</dd>
<dt>Source de journal</dt>
<dd>Source de l'événement (Adresse IP/Nom d'hôte du serveur qui a généré l'événement)</dd>
</dl>

## Gestion du catalogue
{: #catalogmgmt}

Rend compte des événements associés aux activités de gestion du catalogue de services effectuées dans la console d'administration Bluemix.. 

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>SECURITY_MGMT_CONFIG</dt>
<dd>Register template [ID]. Active l'affichage d'un conteneur boilerplate ou d'un environnement d'exécution avec l'ID spécifié sous forme d'option dans le catalogue pour tous les utilisateurs.</dd>
<dd>Deregister template [ID]. Désactive l'affichage d'un conteneur boilerplate ou d'un environnement d'exécution sous forme d'option dans le catalogue pour tous les utilisateurs.</dd>
<dd>Update Service Plan [ID] to public = [ public ] with visibilities = [ ID ]. Active la visibilité du plan de service spécifié. Si public reçoit la valeur true, le plan est visible pour toutes les organisations. Si public est défini à false, vous pouvez indiquer un ensemble d'ID d'organisation pour spécifier quelles organisations ont une visibilité de ce plan de service.</dd>
<dd>Add Service Broker [nom]. Ajoute un courtier de services avec le nom spécifié.</dd>
<dd>Delete Service Broker [nom]. Supprime le courtier de services portant le nom spécifié.</dd>
<dd>Update buildpack [ID]. Met à jour la commande de pack de construction pour celui avec l'ID spécifié.</dd>
<dt>Source de journal</dt>
<dd>Source de l'événement (Adresse IP/Nom d'hôte du serveur qui a généré l'événement)</dd>
</dl>

## Gestion des rapports de sécurité
{: #securityreportsmgmt}

Rend compte des événements associés aux activités de gestion des rapports de sécurité effectuées dans la console d'administration..

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dd>Type d'événement (SECURITY_RUNTIME).
<ul>
<li>SECURITY_DATA_SYNC : Upload report [nom] to category [nom] date [date].
Delete Report with ID [ID]
<li>SECURITY_RESOURCE_ACCESS : Download Report [nom].
</ul>
</dd>
<dt>Utilisateur</dt> 
<dd>Utilisateur qui a lancé l'opération.
<dt>Message</dt> 
<dd>La commande a été exécutée.
<ul>
<li>Upload report [nom] to category [nom] date [date] - Upload. Télécharge un rapport avec le nom de fichier et la date spécifiés dans la catégorie indiquée. 
<li>Delete Report with ID [ID] - Delete. Supprime le rapport avec l'ID spécifié.
<li>Download Report [nom] - Download. Télécharge le rapport avec le nom spécifié.
</ul>
</dd>
<dt>Source de journal</dt>
<dd>Source de l'événement (Adresse IP/Nom d'hôte du serveur qui a généré l'événement)</dd>
</dl>

## Révisions d'accès
{: #accessreviews}

Rend compte des demandes d'accès privilégié à l'environnement Bluemix et de leur traitement par les administrateurs Bluemix. 

### Zones de données

<dl>
<dt>Action_Name</dt>
<dd>Indique la demande d'un utilisateur à faire partie d'un groupe, à renommer un ID utilisateur, à être révoqué en cas de refus, à être retiré d'un groupe (Addp, Rename, Revoke, Delete).</dd>
<dt>Statut</dt>
<dd>Cette zone indique le statut de la demande. Le valideur accepte ou rejette la demande. La demande est en attente d'approbation. L'utilisateur annule la demande (Acceptée, Rejetée, En attente, Annulée).</dd>
<dt>Id_User</dt>
<dd>Nom d'utilisateur</dd>
<dt>User_name</dt> 
<dd>Utilisateur soumettant la demande.</dd>
<dt>Manager_Approval</dt>
<dd>Date à laquelle la demande a été approuvée par le responsable
<dt>Access_Approval</dt>
<dd>Date à laquelle la demande a été approuvée par le responsable du groupe.</dd>
</dl>

## Gestion des clés
{: #keymgmt}

Rend compte des opérations de gestion des clés.

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>Event_Name</dt>
<dd>Type d'événement (Création d'une clé, Création d'un certificat, Suppression d'un certificat).</dd>
<dt>Nom du certificate/de la clé</dt>
<dd>Nom du certificat ou de la clé utilisés.</dd>
<dt>Key_Mgmt_Message</dt> 
<dd>La commande a été exécutée (Création de la clé "nom clé", Création du certificat "nom certificat", configuration du certificat "nom certificat" supprimée).</dd>
<dt>IP de destination</dt>
<dd>Cible de la session.
<dt>Source de journal</dt>
<dd>Source de l'événement.</dd>
</dl>

## Notifications système
{: #systemnotifications}

Rend compte des événements associés à la configuration des fenêtres de déploiement de mise à jour de logiciel ou d'abonnements aux notifications.

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>Event_Type</dt>
<dd>Type d'événement (SECURITY_RUNTIME).
<ul>
<li> SECURITY_MGMT_CONFIG : Create Window [ID].
<li> SECURITY_MGMT_CONFIG : Update Window [ID].
<li> SECURITY_MGMT_CONFIG : Delete Window [ID].
<li> SECURITY_MGMT_CONFIG : Create Subscription [ID].
<li> SECURITY_MGMT_CONFIG : Update Subscription [ID].
<li> SECURITY_MGMT_CONFIG : Delete Susbscription [ID].
<li> SECURITY_MGMT_CONFIG : Create Topic Reply [ID].
</ul>
</dd>
<dt>Utilisateur</dt> 
<dd>L'utilisateur qui a lancé l'opération
<dt>Message</dt>
<dd>La commande a été exécutée.
<ul>
<li>Create Window [ID] - Crée une fenêtre pour mises à jour de maintenance. Les journaux de fenêtres de mise à jour sont générés lorsqu'un utilisateur gère (crée) les fenêtres de mise à jour pour un environnement. Il s'agit des fenêtres d'interruption totale et des fenêtres de préférence pour les déploiements. A ces moments, les clients autorisent/n'autorisent pas l'exécution de déploiements n'entraînant pas d'interruption sans avoir à les approuver ou à les planifier.
<li>Update Window [ID] - Met à jour une fenêtre de maintenance. Cet événement est généré lorsqu'un utilisateur met à jour les fenêtres de mise à jour de maintenance pour un environnement.
<li>SECURITY_MGMT_CONFIG - Supprime une fenêtre de mise à jour. Cet événement est généré lorsqu'un utilisateur délègue les fenêtres de mise à jour d'un environnement.
<li>Create Subscription [ID] - Crée un abonnement à un événement. Les journaux d'audit d'abonnement aux événements sont générés lorsqu'un utilisateur crée un abonnement pour des événements de mise à jour ou d'incident. Ceci leur permet d'être avisés de ces occurrences sur leur système.
<li>Update Subscription [ID] - Met à jour un abonnement à un événement. L'événement est généré lorsqu'un utilisateur met à jour un abonnement à des événements de mise à jour ou d'incident.
<li>Delete Subscription [ID] - Supprime un abonnement à un événement. Cet événement est généré lorsqu'un utilisateur supprime un abonnement à des événements de mise à jour ou d'incident.
<li>Create Topic Reply [ID] - Répond à une rubrique. Le journal d'audit de relecture de rubrique est généré lorsqu'un utilisateur approuve et planifie une mise à jour entraînant des perturbations.
</ul>
</dd>
<dt>Source de journal</dt>
<dd>Source de l'événement (Adresse IP/Nom d'hôte du serveur qui a généré l'événement).</dd>
</dl>

## Administration de la plateforme Bluemix
{: #platformadmin}

Rend compte des événements associés à la plateforme Bluemix par le biais de la ligne de commande, l'API REST, ou l'interface utilisateur Bluemix.

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>Event_Type</dt>
<dd>Type d'événement (SECURITY_RUNTIME).
<ul>
<li>SECURITY_AUTH_CREDS_MODIFY : Evénements associés à la modification de données d'identification d'un utilisateur donné.
<li>SECURITY_MGMT_RESOURCE : Evénements de gestion de resources tels que la création, la suppression et les modifications des attributs d'une ressource.
<li>SECURITY_MGMT_POLICY : Evénement associé à la gestion des règles de sécurité, tel que la création de listes de contrôle d'accès.
<li>SECURITY_RUNTIME : Evénements de l'environnement d'exécution, tel que le démarrage ou l'arrêt de serveurs de sécurité.
<li>SECURITY_RESOURCE_ACCESS : Evénements enregistrant tous les accès à une ressource. Par exemple, tous les accès à un fichier, toutes les requêtes/réponses HTTP à une page Web donnée et tous les accès à une table de base de données critique.
</ul>
</dd>
<dt>Utilisateur</dt> 
<dd>Utilisateur qui a lancé l'opération
<dt>Cible</dt> 
<dd>Détails de l'opération exécutée, tels que l'ID de l'entité et les résultats de l'opération. Exemples :
<ul>
<li>UserCreatedEvent ('["user_id=ca3a811f-1778-4103-9553-537788ed4c4e","username=equaranta"]’). User was created with
(username=equaranta and id = ca3a811f-1778-4103-9553-537788ed4c4e).
<li>GroupModifiedEvent ('{" "group_name":"ops.reports.read","members":["0625ff9a- 8a59-4cca-a80a-8e3b51f3dd21","5005f0f8-e090-4cabb51d- 2ceee70acf0e"}'). Group with name ops.reports.read was modified, with resulting membership (id 0625ff9a- 8a59-4ccaa80a- 8e3b51f3dd21","5005f0f8- e090-4cab-b51d- 2ceee70acf0e).
<li>UserDeletedEvent ('["UserDeletedEvent ('["user_id=5cd5f412-4bbb-4c44-b44b- 713a5bc6144d","username=818811853"]'):"]'. User was deleted with id value=5cd5f412-4bbb- 4c44-b44b-713a5bc6144.
</ul>
</dd>
<dt>Message</dt>
<dd>Entité sur laquelle l'opération a été exécutée (chaîne msg) ou code retour HTTP standard de l'opération (valeur numérique). </dd>
<dt>Composant_plateforme_Bluemix</dt>
<dd>Nom du composant.</dd>
<dt>Source de journal</dt>
<dd>Nom d'hôte/Adresse IP de la source de l'événement.</dd>
<dt>Source</dt>
<dd>Exemple : source de l'événement et adresse IP.</dd>
<dt>Données</dt>
<dd>Informations supplémentaires</dd>
</dl>

## Administration du système d'exploitation
{: #osadmin}

Rend compte des événements générés par Bluemix et susceptibles d'aider au diagnostic des échecs (par exemple, échec du déploiement d'un agent Bosh ou non démarrage d'un service).

### Zones de données

<dl>
<dt>Heure source du journal</dt>
<dd>Date à laquelle l'événement s'est produit.</dd>
<dt>Event_Name</dt>
<dd>Type d'événement (Création d'une clé, Création d'un certificat, Suppression d'un certificat).</dd>
<dt>BMX_key</dt>
<dd>Type de l'opération (BMX_executed_command, BMX_access_unauthorized, BMX_unsuccessful_delete, BMX_sudoers_folder, BMX_Identity_shadow, BMX_extended_attribute, BMX_sudoers).</dd>
<dt>auid</dt> 
<dd>ID utilisateur de la source qui est connecté (par exemple, auid=0 correspond à root, auid=1000 à vcap, auid= 55044 à un utilisateur ldap).</dd>
<dt>numéro d'identification utilisateur (uid)</dt>
<dd>ID utilisateur cible avec lequel la commande est exécutée (par exemple, auid=55044 est connecté et lance une instruction “sudo su” (root) -> uid=0 avant d'exécuter la commande).
<dt>exe_key</dt>
<dd>Commande qui a été exécutée.</dd>
<dt>IP source</dt>
<dd>Adresse IP depuis laquelle l'utilisateur lance la commande.</dd>
<dt>Source de journal</dt>
<dd>Source de l'événement.</dd>
</dl>
