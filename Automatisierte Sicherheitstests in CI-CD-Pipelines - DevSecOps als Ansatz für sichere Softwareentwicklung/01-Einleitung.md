# 1. Einleitung

### 1.1 Motivation und Kontext

Software wird heute in vielen Unternehmen sehr schnell entwickelt und regelmäßig verändert. Neue Funktionen werden oft nicht mehr erst nach langen Projektphasen veröffentlicht, sondern in kurzen Abständen gebaut, getestet und bereitgestellt. Dafür nutzen viele Teams agile Arbeitsweisen, DevOps und CI/CD-Pipelines. Diese Arbeitsweise kann Vorteile bringen, weil Fehler früher sichtbar werden und neue Funktionen schneller bei den Nutzenden ankommen.

Gleichzeitig entsteht dadurch ein Problem für die Sicherheit. Wenn Software sehr schnell entwickelt und veröffentlicht wird, darf Cybersecurity nicht erst am Ende geprüft werden. Sicherheitsprobleme wie unsichere Programmierung, bekannte Schwachstellen in Bibliotheken, falsch gesetzte Berechtigungen oder versehentlich veröffentlichte Zugangsdaten können sonst zu spät erkannt werden. Der Secure Software Development Framework von NIST beschreibt, dass sichere Entwicklungspraktiken in bestehende Entwicklungsprozesse eingebaut werden sollen und nicht nur als zusätzlicher Schritt am Ende verstanden werden dürfen (vgl. NIST, 2022).

Genau an dieser Stelle setzt DevSecOps an. DevSecOps bedeutet, dass Sicherheit als fester Teil von Entwicklung, Betrieb und automatisierten Abläufen verstanden wird. Die Open Worldwide Application Security Project (OWASP) Foundation ist eine gemeinnützige Organisation, die frei zugängliche Projekte, Standards und Hilfen zur Verbesserung der Softwaresicherheit bereitstellt (vgl. OWASP Foundation, o. J.). OWASP beschreibt DevSecOps als Ansatz, um sichere Pipelines aufzubauen und eine Shift-Left-Security-Kultur zu fördern (vgl. OWASP, o. J.-d).

Der Schwerpunkt dieser Arbeit liegt auf automatisierten Sicherheitstests in CI/CD-Pipelines. Solche Tests können zum Beispiel Quellcode, externe Bibliotheken, Zugangsdaten, Container-Images oder eine laufende Anwendung prüfen. Dadurch können Schwachstellen früher sichtbar werden. Aus der Verbindung von schneller Softwareauslieferung und früher Sicherheitsprüfung ergibt sich der konkrete Untersuchungsbedarf dieser Arbeit.

Vor diesem Hintergrund verbindet das Thema die Bereiche Software Engineering und Cybersecurity. Gerade in der Praxis arbeiten Entwicklungsteams häufig mit automatisierten Pipelines. Deshalb wird untersucht, wie Sicherheitstests in diese Abläufe eingebaut werden können, an welchen Stellen sie den größten Nutzen bieten und welche Grenzen dabei entstehen.

### 1.2 Problemstellung

In vielen Softwareprojekten wird Sicherheit noch zu spät geprüft. Häufig finden Sicherheitsprüfungen erst kurz vor der Veröffentlichung oder sogar erst nach dem Deployment statt. Kumar und Goyal beschreiben, dass Sicherheit und Datenschutz bei hohem Zeitdruck teilweise als aufwendig wahrgenommen und deshalb nachrangig behandelt werden. Ihr Modell setzt dem kontinuierliche Sicherheitskontrollen im gesamten Ablauf entgegen (vgl. Kumar und Goyal, 2020). Auch NIST empfiehlt, sichere Entwicklungspraktiken in den bestehenden Softwareentwicklungsprozess zu integrieren, statt sie nur als Endkontrolle zu behandeln (vgl. NIST, 2022).

Ein weiteres Problem ist die starke Abhängigkeit moderner Software von externen Komponenten. Anwendungen verwenden Open-Source-Bibliotheken, Frameworks, Container-Images, Build-Systeme und Cloud-Dienste. Dadurch entstehen zusätzliche Angriffsflächen in der Software-Lieferkette. OWASP nennt unter anderem kompromittierte Abhängigkeiten, unsichere Build-Prozesse und Angriffe auf CI/CD-Systeme als Risiken (vgl. OWASP, o. J.-l). Akbar et al. zeigen zudem, dass fehlende sichere Entwicklungsstandards und fehlende automatisierte Sicherheitstests zu den besonders wichtigen Herausforderungen bei der Einführung von DevSecOps gehören (vgl. Akbar et al., 2022).

Zusätzlich können geheime Zugangsdaten versehentlich in Repositories landen. Dazu gehören zum Beispiel API-Keys, Tokens, Passwörter oder private Schlüssel. GitHub beschreibt Secret Scanning als Verfahren, das die Git-Historie und Repositories auf hartcodierte Zugangsdaten wie API-Keys, Passwörter und Tokens prüfen kann (vgl. GitHub Docs, o. J.). Solche Fehler sind besonders kritisch, weil Angreifer damit unter Umständen Zugriff auf Systeme oder Daten bekommen können.

Daraus ergibt sich die zentrale Problemstellung dieser Arbeit: Sicherheit muss in schnellen Entwicklungsprozessen früher, regelmäßiger und möglichst automatisiert berücksichtigt werden.

Die Forschungsfrage lautet: Wie können automatisierte Sicherheitstests in CI/CD-Pipelines dazu beitragen, Sicherheitsprobleme frühzeitig im Softwareentwicklungsprozess zu erkennen, und welche Vorteile sowie Herausforderungen ergeben sich daraus für das Software Engineering?

### 1.3 Zielsetzung

Ziel der Arbeit ist es, den Ansatz DevSecOps verständlich zu erklären und zu zeigen, wie automatisierte Sicherheitstests in CI/CD-Pipelines eingesetzt werden können. Dabei soll nicht nur beschrieben werden, welche Testarten existieren, sondern auch, an welcher Stelle im Entwicklungsprozess sie sinnvoll eingesetzt werden können.

Die Arbeit soll außerdem zeigen, wie sich DevSecOps vom klassischen DevOps unterscheidet. DevOps verbindet Entwicklung und Betrieb. DevSecOps ergänzt diesen Ansatz um Sicherheit. Dabei geht es nicht nur darum, ein weiteres Tool in eine Pipeline einzubauen. Wichtiger ist eine Arbeitsweise, bei der Sicherheit früh und regelmäßig mitgedacht wird. Diese Sichtweise passt zu der Literatur, die DevSecOps nicht nur als technische Lösung, sondern auch als organisatorischen Ansatz beschreibt (vgl. Rajapakse et al., 2022a; Zhao et al., 2024).

Ein weiteres Ziel ist der Vergleich verschiedener automatisierter Sicherheitstestarten. Dazu gehören SAST, DAST, Dependency Scanning beziehungsweise Software Composition Analysis, Secret Scanning und Container Scanning. Die Arbeit soll zeigen, welche Art von Problem mit welcher Testart erkannt werden kann und warum ein einzelner Test nicht ausreicht.

Am Ende der Arbeit soll bewertet werden, welchen Nutzen DevSecOps für sichere Softwareentwicklung haben kann und welche Schwierigkeiten bei der Einführung entstehen. Vorteile können zum Beispiel frühere Fehlererkennung, regelmäßige Prüfungen und bessere Zusammenarbeit zwischen Entwicklung, Betrieb und Security sein. Herausforderungen können Fehlalarme, zusätzlicher Aufwand, schwierige Tool-Auswahl und fehlendes Security-Wissen im Team sein.

### 1.4 Aufbau des Papers

Die Arbeit ist in fünf Kapitel gegliedert. Kapitel 1 führt in das Thema ein, beschreibt Motivation und Problemstellung, formuliert die Forschungsfrage und erklärt die Zielsetzung der Arbeit.

Kapitel 2 erklärt die wichtigsten Grundlagen. Dazu gehören Software Engineering, sichere Softwareentwicklung, DevOps, DevSecOps, CI/CD-Pipelines und automatisierte Sicherheitstests. Außerdem werden verwandte Arbeiten eingeordnet, damit deutlich wird, welche Aspekte in der Literatur bereits behandelt werden.

Kapitel 3 beschreibt die Methodik. Dort wird erklärt, wie die Literaturrecherche durchgeführt wurde, welche Datenbanken und Suchbegriffe genutzt wurden und nach welchen Kriterien Quellen ausgewählt oder ausgeschlossen wurden.

Kapitel 4 stellt die Ergebnisse dar. Dort werden die Testarten in die Pipeline eingeordnet, anhand fester Kriterien verglichen und anschließend hinsichtlich Vorteilen und Herausforderungen bewertet. Kapitel 5 fasst die Ergebnisse zusammen, beantwortet die Forschungsfrage und nennt Grenzen der Arbeit.

---

[Zur Inhaltsübersicht](README.md) · [Nächstes Kapitel](02-Grundlagen-und-verwandte-Arbeiten.md)
