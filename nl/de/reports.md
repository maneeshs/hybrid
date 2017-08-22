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


# Berichtsdetails nach Typ

## Firewallanmeldungen
{: #firewalllogins}

Berichtet Ereignisse im Zusammenhang mit Administratoranmeldungen an den Vyatta Firewall-Geräten.

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>Ereignisname</dt>
<dd>Ereignisart (fehlgeschlagene Benutzeranmeldung über SSH - falsches Kennwort, Authentifizierungsfehler, Sitzung abschlossen, akzeptiertes Kennwort für den Benutzer, Sitzung geöffnet für den Benutzer).</dd>
<dt>Untergeordnete Kategorie</dt>
<dd>Ereignisdetails (SSH-Anmeldung fehlgeschlagen, Sitzung geschlossen, Hostanmeldung erfolgreich, Sitzung geöffnet).</dd>
<dt>Der Benutzername.</dt> 
<dd>Der Berechtigungsnachweis (Benutzername) des Benutzers, der die Sitzung gestartet hat.</dd>
<dt>Quellen-IP</dt>
<dd>Die IP-Adresse, von der aus der Benutzer die Sitzung startet.
<dt>Ziel-IP</dt>
<dd>Das Ziel der Sitzung.</dd>
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses (der Hostname der Firewall, die das Ereignis generiert hat).</dd>
</dl>

## Zurückgewiesene Firewallanmeldungen
{: #firewalldenies}

Die Berichte, die von Vyatta-Firewall-Geräten generiert werden, wenn eine Zugriffsanforderung aufgrund der geltenden Firewallregeln abgelehnt wird.
  
### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Der Zeitpunkt (Datum und Uhrzeit), zu dem das Ereignis aufgetreten ist.</dd>
<dt>Ereignisname</dt>
<dd>Ereignisart (fehlgeschlagene Benutzeranmeldung über SSH - falsches Kennwort, Authentifizierungsfehler, Sitzung abschlossen, akzeptiertes Kennwort für den Benutzer, Sitzung geöffnet für den Benutzer).</dd>
<dt>Untergeordnete Kategorie</dt>
<dd>Details zum Ereignis der Firewall-Ablehnung</dd>
<dt>Quellen-IP</dt> 
<dd>Die Quellen-IP-Adresse, von der aus die Netzverbindung und/oder der Angriff gestartet wurde.</dd>
<dt>Quellenport</dt>
<dd>Der Protokoll-Zielport.
<dt>Ziel-IP</dt>
<dd>Das Ziel der Sitzung.</dd>
<dt>Zielport</dt>
<dd>Der Protokoll-Zielport.</dd>
<dt>Protokoll</dt>
<dd>Das Kommunikationsprotokoll (tcp/udp).
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses (Hostname der Firewall, die das Ereignis generiert hat).</dd>
<dt>Ereignisanzahl</dt>
<dd>Die Anzahl der Ereignisse dieses Typs.</dd>
</dl>

## Betriebssystemanmeldungen
{: #oslogin}

Berichtet Ereignisse, die vom Betriebssystem generiert werden, wenn ein Administrator eine SSH-Sitzung auf einem Bluemix-System startet.

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>Ereignisname</dt>
<dd>Typ des Ereignisses (Benutzeradressbereichs-Authentifizierung, Fehlschlagen der Benutzeradressbereichs-Authentifizierung)/dd>
<dt>Der Benutzername.</dt> 
<dd>Der Benutzername des Benutzers, der den Authentifizierungsprozess gestartet hat.</dd>
<dt>Quellenadresse</dt>
<dd>Die IP-Adresse, von der aus der Benutzer die Sitzung startet.
<dt>Ziel-IP</dt>
<dd>Das Ziel der Sitzung.</dd>
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses (der Hostname des Servers, von dem aus das Ereignis generiert wurde).</dd>
</dl>

## Anmeldungen über den Anmeldeserver 
{: #loginserverlogins}

Berichtet Ereignisse, die von der Bluemix-Plattform generiert werden, wenn ein Benutzer der Bluemix-Plattform eine Sitzung entweder über die Befehlszeile, über die REST-APIs oder die Bluemix-Konsole startet.

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>Ereignisname</dt>
<dd>Typ des Ereignisses (Benutzeradressbereichs-Authentifizierung, Fehlschlagen der Benutzeradressbereichs-Authentifizierung)/dd>
<dt>Benutzer</dt> 
<dd>Die Benutzer-ID des Benutzers, der den Authentifizierungsprozess gestartet hat.</dd>
<dt>Bluemix_Platform_Component</dt>
<dd>Die Komponente, die das Ereignis (login_server) generiert hat.
<dt>Nachrichtentyp</dt>
<dd>Der Typ der Operation (login, logout).</dd>
<dt>Status</dt>
<dd>Das Ergebnis der Operation (success/failure).</dd>
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses.</dd>
</dl>

## Datenbankverwaltung
{: #dbadmin}

Berichtet Ereignisse im Zusammenhang mit Operationen, die von einem Datenbankadministrator für die internen Bluemix-Datenbanken ausgeführt werden.

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>Event_Type</dt>
<dd>Typ des Ereignisses (SECURITY_RUNTIME).
<dt>Benutzer</dt> 
<dd>Der Benutzername des Benutzers, der die Operation ausgeführt hat. Die folgenden Benutzer sind die Benutzer, die in der Datenbank definiert sind.
<ul>
<li>UAADB: vcap, root, backup_user.
<li>CCDB: vcap, ccadmin, backup_user.
<li>Die Nutzung außerhalb der oben genannten Bereiche erfordert eine Untersuchung, wer die Operation ausgeführt hat. Dies kann mithilfe des Verwaltungssicherheitsberichts des Betriebssystems sowie des Sicherheitsberichts für die Betriebssystemanmeldung geschehen.
</ul>
</dd>
<dt>Quelle</dt> 
<dd>Die IP-Adresse, von der aus der Benutzer den Befehl startet. Folgende Werte werden erwartet:
<ul>
<li>UAADB – uaa VMs und die nfs_WAL_server-VM.
<li>CCDB – api_worker, clock_global, cloud_controller_ng und nsf_WAL_server-VMs.
</ul>
</dd>
<dt>DB_Statement</dt>
<dd>Typ der Operation (alle Datendefinitionsanweisungen, z. B. die Anweisungen CREATE, ALTER und DROP, plus datenverändernde Anweisungen, wie z. B. INSERT, UPDATE, DELETE, TRUNCATE und COPY FROM)</dd>
<dt>DB_Name</dt>
<dd>Name der Datenbank, in der die Operation durchgeführt wurde</dd>
</dl>

## Administrationskonsole - Benutzermanagement
{: #acusermgmt}

Berichtet Benutzerverwaltungsaktivitäten, die für die Bluemix-Konsole ausgeführt werden.

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>Event_Type</dt>
<dd>Typ des Ereignisses (SECURITY_RUNTIME).
<ul>
<li>SECURITY_MGMT_REGISTRY: Benutzer [Benutzer-ID] hinzufügen
<li>SECURITY_MGMT_REGISTRY: Benutzer [Benutzer-ID] löschen
<li>SECURITY_AUTHN_CREDS_MODIFY: Berechtigung [Berechtigungen] zu Benutzern [Benutzer-ID] hinzufügen.
<li>SECURITY_AUTHN_CREDS_MODIFY: Berechtigung [Berechtigungen] von Benutzern [Benutzer-ID] entfernen.
<li>SECURITY_MGMT_CONFIG: Organisation [Name] erstellen.
<li>SECURITY_MGMT_CONFIG: Organisationsmanager [IDs] ändern.
<li>SECURITY_MGMT_CONFIG: Organisations-ID [ID] umbenennen in [Name].
<li>SECURITY_MGMT_CONFIG: Organisations-ID [ID] löschen.
<li>SECURITY_MGMT_CONFIG: Kontingent für Organisation [ID] auf Kontingent [Kontingentplan] aktualisieren.
</ul>
</dd>
<dt>Benutzer</dt> 
<dd>Der Benutzer, der die Operation (LDAP-ID) gestartet hat.
<dt>Nachricht</dt> 
<dd>Ausgeführter Befehl.
<ul>
<li>Hinzufügen von Benutzer [Benutzer-ID]: Fügt einen Benutzer mit der angegebenen ID hinzu.
<li>Löschen von Benutzer [Benutzer-ID]: Löscht einen Benutzer mit der angegebenen ID.
<li>Hinzufügen von Berechtigung [Berechtigungen] für Benutzer [Benutzer-ID]: Fügt Benutzer zu den angegebenen Benutzern hinzu. Die Berechtigungen können folgende sein: ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read, and ops.user.write.
<li>Entfernen von Berechtigung [Berechtigungen] für Benutzer [Benutzer- ID]: Entfernen von Berechtigung - Entfernen von Berechtigungen für die angegebenen Benutzer. Die Berechtigungen können folgende sein: ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read und ops.users.write.
<li>Erstellen von Organisation [Name]: Erstellt eine Organisation mit dem angegebenen Namen.
<li>Ändern von Organisationsmanager [IDs]: Konfiguriert die Manager einer Organisation als angegebene Benutzer.
<li>Umbenennen von Organisation-ID [ID] in Name [Name]: Benennt die angegebene Organisation um.
<li>Löschen von Benutzer [Benutzer-ID]: Löscht einen Benutzer mit der angegebenen ID.
<li>Löschen von Organisations-ID [ID]: Löscht die angegebene Organisation.
<li>Aktualisieren des Kontingents für Organisation [ID] auf Kontingent [Kontingentplan]: Aktualisiert den Kontingentplan für die angegebene Organisation. Zu den Plänen können folgende gehören: q2GB, q4GB, q8GB, q16GB, q32GB, q64GB, q128GB, q256GB, q512GB.
</ul>
</dd>
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses (die IP-Adresse/der Hostname des Servers, der/die das Ereignis generiert hat)</dd>
</dl>

## Katalogverwaltung
{: #catalogmgmt}

Berichtet Ereignisse in Zusammenhang mit Servicekatalogmanagementaktivitäten, die für die Bluemix-Konsole ausgeführt werden. 

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>SECURITY_MGMT_CONFIG</dt>
<dd>Vorlage [ID] registrieren. Aktiviert eine Boilerplate oder Laufzeit mit der angegebenen ID, die als Option im Katalog für alle Benutzer angezeigt wird.</dd>
<dd>Registrierung der Vorlage [ID] zurücknehmen. Bewirkt, dass eine Boilerplate oder Laufzeit nicht mehr als Option im Katalog für alle Benutzer angezeigt wird.</dd>
<dd>Serviceplan [ID] auf 'öffentlich' = [public] mit Sichtbarkeit von = [IDs] aktualisieren. Aktualisiert die Sichtbarkeit des angegebenen Serviceplans. Wenn 'öffentlich' auf 'true' gesetzt ist, ist der Plan für alle Organisationen sichtbar. Ist 'public' auf 'false' gesetzt, kann eine Gruppe von Organisations-IDs bereitgestellt werden, um anzuzeigen, welche Organisationen für diesen Serviceplan sichtbar sind.</dd>
<dd>Service-Broker [Name] hinzufügen. Fügt einen Service-Broker mit dem angegebenen Namen hinzu.</dd>
<dd>Service-Broker [Name] löschen. Löscht den Service-Broker mit dem angegebenen Namen.</dd>
<dd>Buildpack [ID] aktualisieren. Aktualisiert die Buildpack-Bestellung für das Buildpack mit der angegebenen ID.</dd>
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses (die IP-Adresse/der Hostname des Servers, der/die das Ereignis generiert hat)</dd>
</dl>

## Sicherheitsberichtsmanagement
{: #securityreportsmgmt}

Berichtet Ereignisse im Zusammenhang mit den Sicherheitsbericht-Verwaltungsaktionen, die in der Administrationskonsole ausgeführt werden.

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dd>Typ des Ereignisses (SECURITY_RUNTIME).
<ul>
<li>SECURITY_DATA_SYNC: Bericht [Name] mit Datum [Datum] hochladen in Kategorie [Name].
Bericht mit ID [ID] löschen
<li>SECURITY_RESOURCE_ACCESS: Bericht [Name] herunterladen.
</ul>
</dd>
<dt>Benutzer</dt> 
<dd>Der Benutzer, der die Operation gestartet hat.
<dt>Nachricht</dt> 
<dd>Ausgeführter Befehl.
<ul>
<li>Hochladen von Bericht [Name] in Kategorie [Name] mit Datum [Datum]: Hochladen - Hochladen eines Berichts mit dem angegebenen Dateinamen und Datum in die angegebene Kategorie. 
<li>Löschen von Bericht mit ID [ID]: Löschen - Löschen eines Berichts mit der angegebenen ID.
<li>Herunterladen von Bericht [Name]: Herunterladen - Ein Bericht mit den angegebenen Namen wurde heruntergeladen.
</ul>
</dd>
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses (die IP-Adresse/der Hostname des Servers, der/die das Ereignis generiert hat)</dd>
</dl>

## Zugriffsprüfungen
{: #accessreviews}

Berichtet die Anforderungen für berechtigte Zugriffe auf die Bluemix-Umgebung und deren Verarbeitung durch Bluemix-Administratoren. 

### Datenfelder

<dl>
<dt>Action_Name</dt>
<dd>Gibt die Anforderung eines Benutzers an, Teil einer Gruppe zu werden, eine Benutzer-ID umzubenennen, im Falle einer Entlassung widerrufen zu werden oder aus einer Gruppe (Hinzufügen, Umbenennen, Widerrufen, Löschen) entfernt zu werden.</dd>
<dt>Status</dt>
<dd>Dieses Feld gibt den Status der Anforderung an. Der Freigebende akzeptiert die Anforderung oder lehnt sie ab. Die Anforderung wartet auf Genehmigung. Der Benutzer bricht die Anforderung ab (Akzeptiert, Zurückgewiesen, Anstehend, Abgebrochen).</dd>
<dt>Id_User</dt>
<dd>Der Benutzername.</dd>
<dt>User_name</dt> 
<dd>Der Benutzer, der die Anforderung gestellt hat.</dd>
<dt>Manager_Approval</dt>
<dd>Das Datum, an dem die Anforderung durch den Manager genehmigt wurde.
<dt>Access_Approval</dt>
<dd>Das Datum, an dem die Anforderung durch den Gruppenmanager genehmigt wurde.</dd>
</dl>

## Key-Management
{: #keymgmt}

Berichtet Operationen im Zusammenhang mit der Schlüsselzertifikatverwaltung.

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>Event_Name</dt>
<dd>Der Typ des Ereignisses (Schlüssel erstellen, Zertifikat erstellen, Zertifikat löschen).</dd>
<dt>Zertifikats-/Schlüsselname</dt>
<dd>Der verwendete Zertifikats- oder Schlüsselname.</dd>
<dt>Key_Mgmt_Message</dt> 
<dd>Der ausgeführte Befehl (Schlüssel "Schlüsselname" erstellen, Zertifikat "Zertifikatsname" erstellen, Konfiguration für Zertifikat "Zertifikatsname" gelöscht).</dd>
<dt>Ziel-IP</dt>
<dd>Das Ziel der Sitzung.
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses.</dd>
</dl>

## Systembenachrichtigungen
{: #systemnotifications}

Berichtet Ereignisse im Zusammenhang mit der Konfiguration der Fenster für die Bereitstellung von Software-Updates oder der Benachrichtigungsabonnements.

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>Event_Type</dt>
<dd>Typ des Ereignisses (SECURITY_RUNTIME).
<ul>
<li> SECURITY_MGMT_CONFIG: Fenster [ID] erstellen.
<li> SECURITY_MGMT_CONFIG: Fenster [ID] aktualisieren.
<li> SECURITY_MGMT_CONFIG: Fenster [ID] löschen.
<li> SECURITY_MGMT_CONFIG: Abonnement [ID] erstellen.
<li> SECURITY_MGMT_CONFIG: Abonnement [ID] aktualisieren.
<li> SECURITY_MGMT_CONFIG: Abonnement [ID] löschen.
<li> SECURITY_MGMT_CONFIG: Themenantwort [ID] erstellen.
</ul>
</dd>
<dt>Benutzer</dt> 
<dd>Der Benutzer, der die Operation gestartet hat.
<dt>Nachricht</dt>
<dd>Ausgeführter Befehl.
<ul>
<li>Erstellen von Fenster [id] - Erstellt ein Fenster für Wartungsaktualisierungen. Das Aktualisierungsfensterprotokolle werden generiert, wenn ein Benutzer die Aktualisierungsfenster für eine Umgebung verwaltet (erstellt). Die Aktualisierungsfenster sind die Ausfallzeit- und bevorzugten Fenster für Bereitstellungen. Dies trifft zu, wenn Kunden zulassen bzw. nicht zulassen, dass unterbrechungsfreie Bereitstellungen bereitgestellt werden, ohne dass sie diese genehmigen und planen müssen.
<li>Aktualisieren von Fenster [id] - Aktualisiert ein Fenster für Wartungsaktualisierungen. Dieses Ereignis wird generiert, wenn ein Benutzer die Wartungsaktualisierungsfenster für eine Umgebung aktualisiert.
<li>SECURITY_MGMT_CONFIG - Aktualisierungsfenster löschen. Dieses Ereignis wird generiert, wenn ein Benutzer die Aktualisierungsfenster für eine Umgebung delegiert.
<li>Erstellen von Abonnement [id] - Erstellt ein Ereignisabonnement. Die Prüfprotokolle für das Ereignisabonnement werden generiert, wenn ein Benutzer ein Abonnement für Aktualisierungs- oder Störungsereignisse erstellt. Auf diese Weise kann er benachrichtigt werden, wenn im System ein Fehler vorliegt.
<li>Aktualisieren von Abonnement [id] - Aktualisiert ein Ereignisabonnement. Das Ereignis wird generiert, wenn ein Benutzer ein Abonnement für Aktualisierungs- oder Störungsereignisse aktualisiert.
<li>Löschen von Abonnement [id] - Löscht ein Ereignisabonnement. Dieses Ereignis wird generiert, wenn ein Benutzer ein Abonnement für Aktualisierungs- oder Störungsereignisse löscht.
<li>Erstellen von Topicantwort [id] auf ein Topic. Das Prüfprotokoll für Topicantworten wird generiert, wenn der Kunde eine Aktualisierung mit Unterbrechungen genehmigt und plant.
</ul>
</dd>
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses (die IP-Adresse/der Hostname des Servers, der/die das Ereignis generiert hat).</dd>
</dl>

## Bluemix-Plattform - Administration
{: #platformadmin}

Berichtet Ereignisse im Zusammenhang mit der Bluemix-Plattform bei Verwendung der Befehlszeile, der REST-APIs oder der Bluemix-Benutzerschnittstelle.

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>Event_Type</dt>
<dd>Typ des Ereignisses (SECURITY_RUNTIME).
<ul>
<li>SECURITY_AUTH_CREDS_MODIFY: Ereignisse im Zusammenhang mit Änderungen an Berechtigungsnachweisen für eine bestimmte Benutzeridentität.
<li>SECURITY_MGMT_RESOURCE: Ressourcenmanagementereignisse wie z. B. Erstellung, Löschung und Änderungen an den Attributen einer Ressource.
<li>SECURITY_MGMT_POLICY: Ereignis im Zusammenhang mit der Verwaltung von Sicherheitsrichtlinien, z. B. der Erstellung von Zugriffskontrolllisten.
<li>SECURITY_RUNTIME: Laufzeitereignisse wie z. B. das Starten und Stoppen von Sicherheitsservern.
<li>SECURITY_RESOURCE_ACCESS: Ereignisse, die alle Zugriffe auf eine Ressource aufzeichnen. Beispiele sind alle Zugriffe auf eine Datei, alle HTTP-Anforderungen/-Antworten auf eine bestimmte Webseite sowie alle Zugriffe auf eine kritische Datenbanktabelle.
</ul>
</dd>
<dt>Benutzer</dt> 
<dd>Die Person, die die Operation gestartet hat.
<dt>Ziel</dt> 
<dd>Details zur ausgeführten Operation, z. B. die ID der Entität und Ergebnisse der Operation. Beispiele:
<ul>
<li>UserCreatedEvent ('["user_id=ca3a811f-1778-4103-9553-537788ed4c4e","username=equaranta"]’). Der Benutzer wurde mit
(username=equaranta and id = ca3a811f-1778-4103-9553-537788ed4c4e) erstellt.
<li>GroupModifiedEvent ('{" "group_name":"ops.reports.read","members":["0625ff9a- 8a59-4cca-a80a-8e3b51f3dd21","5005f0f8-e090-4cabb51d- 2ceee70acf0e"}'). Die Gruppe mit dem Namen ops.reports.read wurde geändert mit resultierender Mitgliedschaft (id 0625ff9a- 8a59-4ccaa80a- 8e3b51f3dd21","5005f0f8- e090-4cab-b51d- 2ceee70acf0e).
<li>UserDeletedEvent ('["UserDeletedEvent ('["user_id=5cd5f412-4bbb-4c44-b44b- 713a5bc6144d","username=818811853"]'):"]'. Benutzer wurde gelöscht mit id value=5cd5f412-4bbb- 4c44-b44b-713a5bc6144.
</ul>
</dd>
<dt>Nachricht</dt>
<dd>Entität, für die die Operation durchgeführt wurde (Nachrichtenzeichenfolge), oder der Standard-HTTP-Rückgabecode der Operation (numerischer Wert). </dd>
<dt>Bluemix_Platform_Component</dt>
<dd>Der Name der Komponente.</dd>
<dt>Protokollquelle</dt>
<dd>Hostname/IP-Adresse der Quelle des Ereignisses.</dd>
<dt>Quelle</dt>
<dd>Die Quelle des Ereignisses, Beispiel ist die IP-Adresse.</dd>
<dt>Daten</dt>
<dd>Weitere Details.</dd>
</dl>

## Betriebssystemadministration
{: #osadmin}

Berichtet Ereignisse, die von Bluemix generiert wurden und zur Fehlerdiagnose beitragen können (z. B. ein BOSH-Agent, der nicht bereitgestellt werden konnte, oder ein Service, der nicht startet).

### Datenfelder

<dl>
<dt>Zeitpunkt in der Protokollquelle</dt>
<dd>Das Datum, an dem das Ereignis aufgetreten ist.</dd>
<dt>Event_Name</dt>
<dd>Der Typ des Ereignisses (Schlüssel erstellen, Zertifikat erstellen, Zertifikat löschen).</dd>
<dt>BMX_key</dt>
<dd>Typ der Operation (BMX_executed_command, BMX_access_unauthorized, BMX_unsuccessful_delete, BMX_sudoers_folder, BMX_Identity_shadow, BMX_extended_attribute, BMX_sudoers).</dd>
<dt>auid</dt> 
<dd>Die Quellenbenutzer-ID des angemeldeten Benutzers (z. B. auid=0 ist Root, auid=1000 ist VCAP, auid= 55044 ist ein LDAP-Benutzer).</dd>
<dt>uid</dt>
<dd>Die Zielbenutzer-ID, mit der der Befehl ausgeführt wird (z. B. auid=55044 ist angemeldet und führt “sudo su” (root) -> uid=0 durch, bevor er den Befehl ausführt).
<dt>exe_key</dt>
<dd>Befehl ausgeführt.</dd>
<dt>Quellen-IP</dt>
<dd>Die IP-Adresse, von der aus der Benutzer den Befehl startet.</dd>
<dt>Protokollquelle</dt>
<dd>Die Quelle des Ereignisses.</dd>
</dl>
