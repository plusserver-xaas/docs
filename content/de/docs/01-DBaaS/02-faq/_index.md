---
title: "FAQ"
linkTitle: "FAQ"
weight: 10
date: 2023-02-21
---

{{< table_of_contents >}}

## Generelle Fragen
### Was sind DBaaS?
Database as a Service (DBaaS) sind vollständig verwaltete, leistungsstarke Datenbank-Dienste auf Basis der Opensource Datenbanken Mariadb, MySQL oder PostgresSQL. Die Verwendung von voll verwalteten Datenbanken ist eine einfache Alternative zur manuellen Installation, Konfiguration, Wartung und Sicherung von Datenbanken. DBaaS umfasst Monitoring, Entstörung sowie tägliche Backups. DBaaS sind skalierbar und kann so an sich ändernde Leistungsanforderungen angepasst werden. Dazu können die Instanzgrößen (Ram- und CPU Ressourcen) jederzeit angepasst werden, und zwar zu leistungsfähigerer Instanzgrößen, um Performanceengpässe zu überbrücken aber auch in die Gegenrichtung. Der Datenspeicher kann jederzeit in festen 50GB Schritten erhöht werden. Der Zugriff auf die Daten wird durch die Festlegung auf feste, für den Zugriff auf die Datenbank erlaubte IPs und TLS Verschlüsselten Datentransfer abgesichert. Sollte es zu Fehlern kommen kann jederzeit ein Backupstand bereitgestellt werden. Dazu wird ein neuer DBaaS mit den Backupdaten bereitgestellt. Dieser Mechanismus kann auch genutzt werden, um zusätzlich Datenbanken für Test und Entwicklung bereitzustellen.

### Was sind die unterstützten DBMS?
* **MariaDB**
* **MySQL**
* **PostgreSQL**

### Kann ich DBaaS mit anderen Plusserver-Produkten verbinden?
Ja, sofern die Produkte über ein öffentliches Netzwerk erreichen können.

### Was ist eine Major- und eine Minorversion?
Jede Software, auch Datenbanksoftware, bietet neuere Versionen ihres Codes an, die in der Regel Fehlerkorrekturen, Sicherheitsverbesserungen und Verbesserungen enthalten. Im Allgemeinen umfasst ein Minor-Versions-Upgrade nur Änderungen, die mit bestehenden Anwendungen abwärtskompatibel sind. Im Gegensatz dazu kann eine Majorversion Inkompatibilitäten mit sich bringen.

### Was sind Regionen und Availability Zones (AZ)? {#Regions}

PlusServer bietet mehrere Regionen und Verfügbarkeitszonen (AZs), um Kunden Hochverfügbarkeit und Disaster-Recovery-Optionen zu bieten. Jede AZ besteht aus einem oder mehreren Rechenzentren, die so konzipiert sind, dass sie unabhängig voneinander sind und im Falle von Ausfällen oder Katastrophen Redundanz bieten. Kunden können wählen, ob sie ihre Ressourcen in einer oder mehreren AZs für Hochverfügbarkeit und Disaster Recovery einsetzen wollen.

#### Was ist eine Region
Eine Region ist ein geografisches Gebiet, das aus mehreren isolierten und räumlich getrennten, also redundanten AZs besteht.

##### Anforderungen

* Besteht aus mehreren isolierten und räumlich getrennten AZ innerhalb eines geografischen Gebiets.
* Die Entfernung zwischen den Regionen beträgt >=300 km.

##### Beispiel

* DE-WEST

#### Was ist eine Availability Zone (AZ)?

Eine Verfügbarkeitszone (AZ) ist ein Standort innerhalb einer Region, der aus einem oder mehreren Rechenzentren besteht, die so konzipiert sind, dass sie voneinander unabhängig sind und im Falle von Ausfällen oder Katastrophen Redundanz bieten. Kunden können ihre Ressourcen in einer oder mehreren AZs für Hochverfügbarkeit und Disaster Recovery bereitstellen.

##### Anforderungen

* Liegt innerhalb einer Region und besteht aus einem oder mehreren Rechenzentren mit mindestens einer gemeinsamen Strom-, Netzwerk- und Kühlungsversorgung.
* Ein AZ ist immer unabhängig von einem anderen (insbesondere in den Bereichen Strom [Einspeisung, Verteilung, USV, Notstrom], Netzwerk [Einspeisung, Router, Switches], Kühlung und Gebäude).
* Die Latenzzeit zwischen den AZs innerhalb derselben Region beträgt <=2ms.

##### Beispiel

* DE-NORTH-1
* DE-WEST-2

#### Plusserver Regionen und AZ Liste {#Regionlist}

In der folgenden Tabelle sind die vom PlusServer angebotenen Regionen und AZs aufgeführt:

| Region   | Availability Zone | Standort               |
|----------|-------------------|------------------------|
| DE-NORTH | DE-NORTH-1        | Hamburg, Deutschland   |
|          | DE-NORTH-2        | Hamburg, Deutschland   |
| DE-WEST  | DE-WEST-1         | Köln, Deutschland      |
|          | DE-WEST-2         | Düsseldorf, Deutschland|

### Wie kann ich die DBMS-Version bei der Erstellung einer DB-Instanz auswählen?
Aktuell bieten wir nur je eine Version je DBaaS. Wir planen weitere Versionen jeder DBaaS zur Auswahl zu stellen.

### Kann ich eine neue Version vor dem Upgrade testen?
Da wir aktuell nur eine Version zur Auswahl stellen gibt es keinen Möglichkeit zum Upgrade und zum Test des Upgradesc

### Wo kann ich die Produkt-Roadmap finden?
Comming soon

## Abrechnung
### Wie werden die Dienste abgerechnet?
Pay as you go

### Wo kann ich meine Rechnungen finden?
Ihre Rechnung finde Sie im Kundenportal unter ***Verträge und Abrechnungen*** / ***Rechnungen***
https://customerservice.plusserver.com/billing/invoices

### Was ist in den Preisen enthalten?
* Durch TLS und IP-Zugriffsbeschränkung abgesicherter Zugriff  
* Buchung und Skalierung direkt über das Kundenportal
* Abrechnung nach "Pay as you go"
* Plusserver stellt die passende Infrastruktur bereit
* Plusserver betreibt die DBaaS im 24/7 Betrieb
* Plusserver spielt regelmäßig sicherheitsrelevante Updates ein
* Plusserver richtet ein tägliches Backup ein und hält 7 Backups vor
* Plusserver überwacht und entstört die DBaaS
* Ein Wechsel zu einer andere Nodegröße ist möglich
* Die Datenfestplatte kann vergrößert werden

### Gibt es Limitierungen
* Defaultdatenbank und Superuser können nicht verändert oder gelöscht werden
  * Das Superuserrecht verbleibt bei PlusServer
  * Die Rechte werden von PlusServer für Backup und Monitoring benötigt
* Erreichbarkeit der Datenbank ausschließlich über eine Public IP (IPv4)
  * keine VPN Tunnel möglich
  * keine direkte Verbindung zu anderen Produkten
* Der Zugriff auf den Service ist nur von explizit freigegebenen IPs / IP-Netzen möglich (IP Whitelisting)
  * Freizugebende IPs / IP-Netze müssen über Plusserver eingerichtet werden
  * Es dürfen keine Any-Freigaben (Zugriff von 0.0.0.0) erfolgen
  * Freigaben von IP-Netzen dürfen nur im Bereich /24 - /32 (für IPv4) liegen
* Die Datenfestplatte kann nur vergrößert werden. Für eine Verkleinerung der Datenplatte muss ein neuer DBaaS gebucht werden und die Daten müssen exportiert/importiert werden 

### Wann beginnt und endet die Abrechnung?
* Die Abrechnung erfolgt je voller Stunde
* Die Abrechnung startet mit der nächsten vollen Stunde nach erfolgreicher Bereitstellung des DBaaS.
* Die Abrechnung endet mit der vollen Stunde der Kündigung des DBaaS. Diese Stunde wird noch voll abgerechnet.

### Ist der eingehende und ausgehende Netzwerkverkehr enthalten?
Jeglicher Traffic von und zu dem Service ist im Preis enthalten

### Wie ist die Verfügbarkeit
Die Infrastruktur ist vollständig redundant aufgebaut. Wir garantieren daher eine SLA von 99,95.

## Bereitstellung
### Wie viele DBaaS-Instanzen kann ich betreiben?
Aktuell gibt es keine Limitierung

### Wie fange ich an?
Wir haben für Sie eine [Schnellstartanleitung](https://docs.xaas.get-cloud.io/de/docs/01-dbaas/01-quickstart/) erstellt 

### Wie kann ich Daten in eine DB-Instanz importieren?
Wir verwenden offizielle Versionen der DBMS, so dass Sie sich auf die offizielle Dokumentation für jedes DBMS verlassen können, um Daten in DBaaS zu importieren. Für PostgreSQL können Sie zum Beispiel pg_dump und pg_restore verwenden, für MySQL oder MariaDB mysqldump und mysqlimport.

## Skalierung
### Wie kann ich eine andere Nodegröße auswählen?
Cooming Soon

### Kann ich den Datenspeicher verkleinern?
Nein, eine Reduzierung des genutzten Speichers ist nicht vorgesehen. Sie können hier mit Export/Import die Daten in einen neuen DBaaS umziehen um den Speicher wieder zu verringern.

### Wird meine DB-Instanz während der Skalierung verfügbar bleiben?
#### Nodesize
Hier wird es eine kurze Unterbrechung geben, da die Node mit angepassten Ressourcen neu ausgerollt wird. 
#### Speicherplatz
Der Datenspeicher wir ohne Unterbrechnung erweitert

### Wie ist die Leistung der einzelnen Nodegrößen?
Wir stellen bisher keine Benchmark-Ergebnisse für DBaaS zur Verfügung. Jeder geschäftliche Anwendungsfall ist anders, und die Benchmarks können sich stark von Ihren eigenen realen Anwendungsfällen unterscheiden. Beachten Sie jedoch, dass unsere Leistungsunterschiede linear sind.

### Wo werden meine DB-Instanzen bereitgestellt?
Das hängt von der Auswahl der Region ab, die Sie ausgewählt haben. Weiter Informationen finden sie hier [Plusserver Regionen und AZ Liste](#Regionlist)

### Bieten wir Multi-AZ-Bereitstellungen an?
Bislang bieten wir keine Multi-AZ-Bereitstellungen an. Sie bekommen die DBaaS in jeweils einer Region bzw einem AZ bereitgestellt.

## Backups und Wartung
### Wie führen Sie Backups durch?
Ja, wir erstellen ein tägliches Backup der Daten

### Kann ich manuelle Backups durchführen?
Wir verwenden offizielle Versionen von DBMS, so dass Sie sich auf die offizielle Dokumentation für jedes DBMS verlassen können, um Backups für Public Cloud-Datenbanken durchzuführen. Für PostgreSQL können Sie zum Beispiel pg_dump und pg_restore verwenden. Für MySQL können Sie mysqldump und mysqlimport verwenden.

### Kann ich die von Plusserver erstellten Backups direkt herunterladen?
Nein, Sie können die von Plusserver erstellten Backups nicht direkt herunterladen.

### Wo werden meine Backups gespeichert, und wie lange?
Die Backupdaten werden auf ein abgesichertes S3 Storage ausgelagert und dort 7 Tage vorgehalten
 
### Was ist ein Wartungsfenster? Wird meine DB-Instanz während der Wartungsarbeiten verfügbar sein?
Die Backups werden ab 22:00 erstellt. Wir erstellen die Backups auf Snapshotbasis. Die Datenbank bleibt daher grundsätzlich verfügbar, wird aber für einen kurzen Moment in einen konsistenten Zustand gebracht (Read only).
 
### Kann ich das Wartungsfenster ändern?
Derzeit können Sie das Wartungsfenster nicht ändern

## Sicherheit
### Welche Sicherheitsmechanismen gibt es für meine Datenbankinstanz?
* Die Datenbank kann nur nach expliziter Freischaltung von berechtigten IPs oder IP-Bereichen genutzt werden. Wir empehlen dies so stark wie möglich einzugrenzen
* Sie können ausschließlich SSL verschlüsselt mit der Datenbank verbinden  

### Wer kann anfangs auf meine Datenbankinstanz zugreifen?
Solange keine Freischaltungen vorgenommen wurden: Niemand

### Wie kann ich die Zugriffsrechte auf meine Datenbankinstanz verwalten?
Comming Soon

### Wie kann ich neue Benutzer für meine Datenbankinstanz hinzufügen?
Wir haben dazu einen kleinen Anleitungsartikel geschrieben: [Anlegen neuer Datenbanken und Benutzer](https://docs.xaas.get-cloud.io/de/docs/01-dbaas/03-howto/anlegen-neuer-datenbanken-und-user/)

### Sind meine Daten verschlüsselt?
TODO

### Zertifizierungen
TODO

### Kann ich eine Verbindung zu meiner Datenbankinstanz über ein öffentliches Netzwerk herstellen?
TODO


## Fehlersuche
### Meine Abfragen sind langsam
TODO

### Meine Daten sind beschädigt
Wenn Ihre Daten beschädigt sind, haben Sie 2 Möglichkeiten:

1. Wenn Ihre Daten wichtig sind, können Sie eine Sicherungskopie wiederherstellen, auf der Ihre Daten noch gültig sind. Für diesen Schritt müssen Sie selbst Nachforschungen anstellen.
2. Wenn Ihre Daten gelöscht werden können, können Sie den Datenbankinstanzdienst löschen und einen neuen erstellen oder einfach der offiziellen DBMS-Dokumentation folgen, um alle Daten zu löschen.

