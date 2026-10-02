# 3. Methodik

### 3.1 Art der Arbeit

Die Arbeit wurde als Literaturarbeit erstellt. Die Forschungsfrage wurde auf Grundlage vorhandener wissenschaftlicher und fachlicher Quellen beantwortet. Es wurde keine eigene Umfrage und kein eigenes technisches Experiment durchgeführt. Stattdessen wurden geeignete Quellen gesucht, gelesen, verglichen und zusammengeführt.

Diese Vorgehensweise passt zum Thema, weil DevSecOps bereits in vielen wissenschaftlichen und fachlichen Quellen behandelt wird. Außerdem geht es in dieser Arbeit nicht darum, ein bestimmtes Tool praktisch zu messen, sondern darum, den Einsatz automatisierter Sicherheitstests in CI/CD-Pipelines einzuordnen und zu bewerten.

### 3.2 Recherchequellen und Datenbanken

Für die Literaturrecherche wurden wissenschaftliche Datenbanken und ergänzende fachliche Quellen kombiniert. Wissenschaftliche Beiträge wurden vor allem über ACM Digital Library, IEEE Xplore, SpringerLink, ScienceDirect und Google Scholar gesucht. Neben Überblicksarbeiten wurden auch konzeptionelle Studien, empirische Untersuchungen und Fallstudien aufgenommen, damit der Ergebnisteil nicht nur Begriffe erklärt, sondern konkrete Pipeline-Erweiterungen und organisatorische Folgen einordnen kann.

Ergänzend wurden anerkannte Praxisquellen verwendet, vor allem OWASP, NIST, GitHub Docs, OWASP ZAP und OpenSSF/SLSA. Diese Quellen ersetzen die wissenschaftliche Literatur nicht. Sie werden dort eingesetzt, wo konkrete Standards, Testarten, Sicherheitsanforderungen oder technische Hinweise beschrieben werden. In der Auswertung wird daher klar zwischen peer-reviewter Forschung und fachlichen Praxisquellen unterschieden.

### 3.3 Suchbegriffe und Suchstrings

Die Recherche begann mit allgemeinen Suchbegriffen. Dazu gehörten DevSecOps, DevOps Security, CI/CD Security, Secure Software Development und Automated Security Testing. Danach wurden genauere Begriffe verwendet, zum Beispiel Static Application Security Testing, Dynamic Application Security Testing, Software Composition Analysis, Dependency Scanning, Secret Scanning, Container Scanning und Shift Left Security.

Beispielhafte Suchstrings waren: DevSecOps AND Software Engineering, DevSecOps AND CI/CD, Security Testing AND CI/CD Pipeline, Secure Software Development AND DevSecOps, Automated Security Testing AND DevOps sowie Shift Left Security AND DevOps. Diese Suchstrings wurden je nach Datenbank angepasst, weil nicht jede Datenbank dieselben Suchfunktionen verwendet.

Bei der Suche wurde außerdem darauf geachtet, dass die Quellen einen klaren Bezug zur Forschungsfrage haben. Quellen waren besonders relevant, wenn sie erklären, wie Sicherheit in DevOps oder CI/CD integriert werden kann, welche Testarten dafür geeignet sind oder welche Herausforderungen bei der Einführung entstehen.

### 3.4 Ein- und Ausschlusskriterien

Bei der Auswahl der Quellen wurde zuerst der Titel geprüft. Danach wurde das Abstract gelesen. Wenn eine Quelle zum Thema passte, wurde der Text genauer betrachtet. Wichtig war ein klarer Bezug zu DevSecOps, CI/CD-Pipelines, automatisierten Sicherheitstests oder sicherer Softwareentwicklung.

Eingeschlossen wurden wissenschaftliche Quellen wie Konferenzbeiträge, Zeitschriftenartikel und Bücher. Fachliche Quellen wurden genutzt, wenn sie von anerkannten Organisationen stammen oder direkt für das Thema wichtig sind. Dazu gehören zum Beispiel OWASP, NIST, OpenSSF und offizielle Tool-Dokumentationen.

Ausgeschlossen wurden Quellen ohne klaren Bezug zur Forschungsfrage. Reine Werbetexte, unklare Blogbeiträge und Quellen ohne erkennbare Autorenschaft wurden nicht als Hauptquellen verwendet. Blogbeiträge dienten höchstens als Einstieg, aber nicht als zentrale Grundlage der Arbeit.

### 3.5 Methode zur Beantwortung der Forschungsfrage

Die Forschungsfrage wurde in mehrere Teilfragen aufgeteilt. Zuerst wurde geklärt, was DevSecOps bedeutet und wie es sich von DevOps unterscheidet. Danach wurde untersucht, welche Rolle CI/CD-Pipelines für moderne Softwareentwicklung spielen. Anschließend wurden verschiedene Sicherheitstestarten beschrieben und miteinander verglichen.

Der Vergleich erfolgte anhand fester Kriterien. Betrachtet wurden der Einsatzzeitpunkt in der Pipeline, das geprüfte Objekt, typische Sicherheitsprobleme, Stärken und Grenzen. Dadurch wurde verhindert, dass die Arbeit nur Toolnamen aufzählt. Stattdessen wurde sichtbar, welche Testart welchen Beitrag zu einer sicheren Pipeline leisten kann.

Danach wurden Vorteile und Herausforderungen aus der Literatur gesammelt und geordnet. Zu den Vorteilen gehören frühere Fehlererkennung, regelmäßige Prüfungen und bessere Zusammenarbeit. Zu den Herausforderungen gehören Fehlalarme, zusätzlicher Aufwand, fehlendes Sicherheitswissen und die Gefahr, sich zu stark auf Tools zu verlassen.

Die Quellen wurden nicht nur einzeln zusammengefasst, sondern miteinander verbunden. Wenn mehrere Quellen ähnliche Punkte nannten, wurde daraus ein gemeinsames Muster abgeleitet. Unterschiedliche Schwerpunkte wurden in der Auswertung berücksichtigt. Dadurch beschreibt die Arbeit nicht nur, sondern vergleicht und bewertet die Ergebnisse.

### 3.6 Grenzen der Methodik

Die Arbeit hat einige Grenzen. Da es sich um eine Literaturarbeit handelt, werden keine eigenen Messwerte aus einer echten CI/CD-Pipeline erhoben. Es wird also nicht praktisch getestet, wie schnell ein bestimmtes Tool arbeitet oder wie viele Schwachstellen es findet. Die Bewertung erfolgt auf Grundlage vorhandener Literatur und fachlicher Quellen.

Eine weitere Grenze ist, dass sich Tools und Best Practices im Bereich DevSecOps schnell verändern. Neue Tools entstehen, alte Tools ändern sich und Sicherheitsanforderungen entwickeln sich weiter. Deshalb wird in der Arbeit eher der grundsätzliche Einsatz von Testarten betrachtet und weniger ein einzelnes Tool als dauerhaft beste Lösung dargestellt.

Außerdem kann die Arbeit nicht alle möglichen Sicherheitstests vollständig behandeln. Der Schwerpunkt liegt auf SAST, DAST, Dependency Scanning, Secret Scanning und Container Scanning, weil diese Testarten besonders gut zu CI/CD-Pipelines passen und häufig im Zusammenhang mit DevSecOps genannt werden.

### 3.7 Hinweis zur Arbeitsweise und zu verwendeten Hilfsmitteln

Bei der Erstellung dieser Arbeit wurden digitale Hilfsmittel zur sprachlichen Überarbeitung, Strukturierung und Formatkontrolle genutzt. Die inhaltliche Auswahl der Quellen, die Bewertung der Aussagen und die Verantwortung für den Text liegen beim Verfasser. Alle übernommenen Gedanken aus fremden Quellen werden im Text durch Quellenverweise gekennzeichnet und im Literaturverzeichnis aufgeführt.

Dieser Hinweis dient der Transparenz. Die Arbeit soll dadurch nachvollziehbar machen, welche Rolle Hilfsmittel hatten: Sie unterstützen bei Formulierung und Ordnung des Textes, ersetzen aber nicht die eigene Prüfung der Quellen und die fachliche Auseinandersetzung mit dem Thema.

---

[Zur Inhaltsübersicht](README.md) · [Vorheriges Kapitel](02-Grundlagen-und-verwandte-Arbeiten.md) · [Nächstes Kapitel](04-Ergebnisse-und-Bewertung.md)
