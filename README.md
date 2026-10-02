# Automatisierte Sicherheitstests in CI/CD-Pipelines

**DevSecOps als Ansatz für sichere Softwareentwicklung**  
Literaturarbeit von **Firas Massoussi** · Hochschule Bonn-Rhein-Sieg

## Überblick

Diese Arbeit untersucht, wie automatisierte Sicherheitstests in CI/CD-Pipelines Sicherheitsprobleme frühzeitig sichtbar machen können. Im Mittelpunkt stehen DevSecOps, Shift Left Security und das Zusammenspiel technischer Prüfungen mit klaren Prozessen und gemeinsamer Verantwortung.

Das Repository dokumentiert eine Literaturarbeit im Studiengang **Cyber Security & Privacy**, Modul **Literatur-Seminar**, bei **Prof. Dr. Hackelöer**. Es enthält die schriftliche Arbeit sowie die Unterlagen zum Abschlussvortrag.

## Dokumente

| Dokument | Datei |
| --- | --- |
| Schriftliche Arbeit | [Vollständige Arbeit direkt lesen](dokumentation/README.md) |
| Abschlussvortrag als PDF | [Abschlussvortrag.pdf](praesentation/Abschlussvortrag.pdf) |
| Bearbeitbare PowerPoint-Präsentation | [Abschlussvortrag.pptx](praesentation/Abschlussvortrag.pptx) |

Die vollständige schriftliche Arbeit ist im Ordner `dokumentation` direkt als Markdown lesbar. Der Abschlussvortrag liegt in einer ausgewählten PDF-Fassung mit „Grenze & Ausblick“ auf der Schlussfolie vor. Die bearbeitbare PowerPoint-Datei bleibt zusätzlich verfügbar.

## Forschungsfrage

Wie können automatisierte Sicherheitstests in CI/CD-Pipelines dazu beitragen, Sicherheitsprobleme frühzeitig im Softwareentwicklungsprozess zu erkennen, und welche Vorteile sowie Herausforderungen ergeben sich daraus für das Software Engineering?

## Untersuchte Sicherheitstests

Die folgende Übersicht fasst die Einordnung in der Arbeit zusammen:

| Testart | Prüfobjekt | Typische Einordnung in der Pipeline |
| --- | --- | --- |
| SAST | Quellcode | Commit, Pull Request oder Build |
| DAST | Laufende Anwendung | Testumgebung |
| SCA / Dependency Scanning | Externe Bibliotheken und Abhängigkeiten | Build |
| Secret Scanning | Zugangsdaten im Code und in der Git-Historie | Commit oder Pull Request |
| Container Scanning | Container-Images und enthaltene Pakete | Vor dem Deployment |

## Zentrale Ergebnisse der Literaturarbeit

- Unterschiedliche Testarten ergänzen sich, weil sie verschiedene Prüfobjekte und Risiken abdecken.
- Frühe und regelmäßige Prüfungen können schnellere Rückmeldungen und bessere Nachvollziehbarkeit ermöglichen.
- Die Bewertung und Bearbeitung von Funden benötigt klare Zuständigkeiten und Security-Wissen.
- Fehlalarme, Pflegeaufwand und die Auswahl geeigneter Werkzeuge bleiben Herausforderungen.
- Auch die CI/CD-Infrastruktur selbst muss geschützt werden.

## Umfang und Grenzen

Die Bewertung basiert auf wissenschaftlicher und fachlicher Literatur. Im Rahmen der Arbeit wurde keine eigene CI/CD-Pipeline implementiert und keine praktische Messung von Erkennungsrate, Fehlalarmen oder Laufzeit durchgeführt. Dieses Repository enthält daher Dokumentation und Präsentationsmaterialien.

Als weiterführende Untersuchung wird eine praktisch umgesetzte Beispiel-Pipeline mit Messungen zu Laufzeit, Fehlalarmen und Sicherheitsfunden vorgeschlagen.

## Quellen

Das vollständige [Literatur- und Quellenverzeichnis](dokumentation/README.md#literatur--und-quellenverzeichnis) befindet sich am Ende der schriftlichen Arbeit.

## Autor

**Firas Massoussi**  
Cyber Security & Privacy · Hochschule Bonn-Rhein-Sieg
