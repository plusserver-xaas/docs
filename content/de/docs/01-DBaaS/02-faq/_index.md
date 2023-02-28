---
title: "FAQ"
linkTitle: "FAQ"
weight: 2
date: 2023-02-21
description: >
  See your project in action!
---

## Generelle Fragen
#### Was sind DBaaS?
{{< alert >}}
TODO

{{< /alert >}}
### Was sind die unterstützten DBMS?
{{< alert >}}
**MariaDB**
**MySQL**
**PostgreSQL**
{{< /alert >}}
### Kann ich DBaaS mit anderen Plusserver-Produkten verbinden?
{{< alert >}}
Ja, sofern die Produkte über ein öffentliches Netzwerk erreichen können.
{{< /alert >}}
### Was ist eine Major- und eine Minorversion?
Jede Software, auch Datenbanksoftware, bietet neuere Versionen ihres Codes an, die in der Regel Fehlerkorrekturen, Sicherheitsverbesserungen und Verbesserungen enthalten. Im Allgemeinen umfasst ein Minor-Versions-Upgrade nur Änderungen, die mit bestehenden Anwendungen abwärtskompatibel sind. Im Gegensatz dazu kann eine Majorversion Inkompatibilitäten mit sich bringen.
### Wie kann ich die DBMS-Version bei der Erstellung einer DB-Instanz auswählen?
TODO

### Kann ich eine neue Version vor dem Upgrade testen?
TODO

### Wo kann ich die Produkt-Roadmap finden?
TODO

## Abrechnung
### Wie werden die Dienste abgerechnet?
Pay as you go
### Wo kann ich meine Rechnungen finden?
TODO

### Was ist in den Preisen enthalten?
TODO

### Wann beginnt und endet die Abrechnung?
TODO

### Ist der eingehende und ausgehende Netzwerkverkehr enthalten?
Jeglicher Traffic von und zu dem Service ist im Preis enthalten

## Bereitstellung
### Wie viele DBaaS-Instanzen kann ich betreiben?
Aktuell gibt es keine Limitierung

### Wie fange ich an?
TODO

### Wie kann ich Daten in eine DB-Instanz importieren?
Wir verwenden offizielle Versionen der DBMS, so dass Sie sich auf die offizielle Dokumentation für jedes DBMS verlassen können, um Daten in DBaaS zu importieren. Für PostgreSQL können Sie zum Beispiel pg_dump und pg_restore verwenden, für MySQL oder MariaDB mysqldump und mysqlimport.

## Skalierung
### wie kann ich eine andere Nodegröße auswählen
TODO

### Kann ich den Datenspeicher verkleiner
Nein, eine Reduzierung des genutzten Speichers ist nicht vorgesehen. Sie können hier mit Export/Import die Daten in einen neuen DBaaS umziehen um den Speicher wieder zu verringern.
### Wird meine DB-Instanz während der Skalierung verfügbar bleiben?
TODO

### Wie ist die Leistung der einzelnen Nodegrößen?
Wir stellen bisher keine Benchmark-Ergebnisse für DBaaS zur Verfügung. Jeder geschäftliche Anwendungsfall ist anders, und die Benchmarks können sich stark von Ihren eigenen realen Anwendungsfällen unterscheiden. Beachten Sie jedoch, dass unsere Leistungsunterschiede linear sind.
### Wo werden meine DB-Instanzen bereitgestellt?
TODO

### Bieten wir Multi-AZ-Bereitstellungen an?
Bislang bieten wir keine Multi-AZ-Bereitstellungen an. 
## Backups und Wartung
### Wie führen Sie Backups durch?
TODO

### Kann ich manuelle Backups durchführen?
Wir verwenden offizielle Versionen von DBMS, so dass Sie sich auf die offizielle Dokumentation für jedes DBMS verlassen können, um Backups für Public Cloud-Datenbanken durchzuführen. Für PostgreSQL können Sie zum Beispiel pg_dump und pg_restore verwenden. Für MySQL können Sie mysqldump und mysqlimport verwenden.

### Kann ich die von Plusserver erstellten Backups direkt herunterladen?
Nein, Sie können die von Plusserver erstellten Backups nicht direkt herunterladen.

### Wo werden meine Backups gespeichert, und wie lange?
TODO
 
### Was ist ein Wartungsfenster? Wird meine DB-Instanz während der Wartungsarbeiten verfügbar sein?
TODO
 
### Kann ich das Wartungsfenster ändern?
Derzeit können Sie das Wartungsfenster nicht ändern

## Sicherheit
### Welche Sicherheitsmechanismen gibt es für meine Datenbankinstanz?
TODO

### Wer kann anfangs auf meine Datenbankinstanz zugreifen?
TODO

### Wie kann ich die Zugriffsrechte auf meine Datenbankinstanz verwalten?
TODO

### Wie kann ich neue Benutzer für meine Datenbankinstanz hinzufügen?
TODO

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

