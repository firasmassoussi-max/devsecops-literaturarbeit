# 5. Fazit

Die Forschungsfrage lautete: Wie können automatisierte Sicherheitstests in CI/CD-Pipelines dazu beitragen, Sicherheitsprobleme frühzeitig im Softwareentwicklungsprozess zu erkennen, und welche Vorteile sowie Herausforderungen ergeben sich daraus für das Software Engineering?

Die Arbeit kommt zu dem Ergebnis, dass automatisierte Sicherheitstests Sicherheitsprobleme früher sichtbar machen können, wenn sie sinnvoll in verschiedene Phasen der Pipeline eingebaut werden. SAST und Secret Scanning eignen sich besonders früh im Prozess, weil sie bereits beim Commit, Pull Request oder Build eingesetzt werden können. Dependency Scanning beziehungsweise SCA passt gut in die Build-Phase, weil dort Abhängigkeiten sichtbar sind. DAST prüft eine laufende Anwendung und eignet sich deshalb eher für eine Testumgebung. Container Scanning ist besonders vor dem Deployment sinnvoll, wenn das fertige Container-Image geprüft wird.

Die Vorteile von DevSecOps liegen vor allem in früherer Rückmeldung, regelmäßigen Prüfungen, besserer Nachvollziehbarkeit und stärkerer Zusammenarbeit zwischen Entwicklung, Betrieb und Security. Gleichzeitig zeigt die Arbeit, dass DevSecOps nicht automatisch alle Sicherheitsprobleme löst. Herausforderungen sind Fehlalarme, zusätzlicher Aufwand, Tool-Auswahl, fehlendes Security-Wissen und die Gefahr, sich zu stark auf automatisierte Tools zu verlassen.

Für das Software Engineering ist DevSecOps deshalb ein sinnvoller Ansatz, wenn es als Gesamtsystem verstanden wird. Die Literatur zeigt, dass technische Kontrollen, sichere Praktiken, geschützte Infrastruktur und Zusammenarbeit gemeinsam erforderlich sind. Automatisierte Tests liefern frühe und wiederholbare Rückmeldungen; ihren tatsächlichen Nutzen erreichen sie aber erst durch klare Zuständigkeiten, risikobasierte Security Gates und eine fachliche Bewertung der Ergebnisse. Damit besteht die zentrale Verbesserung gegenüber einem reinen DevOps-Prozess nicht nur aus zusätzlichen Scannern, sondern aus einer durchgängigen Sicherheitsverantwortung von der Planung bis zum Monitoring.

Die Arbeit hat auch Grenzen. Es wurde keine eigene praktische Messung durchgeführt. Es wurde also nicht getestet, wie schnell oder genau einzelne Tools in einer echten Pipeline arbeiten. Die Bewertung basiert auf wissenschaftlicher und fachlicher Literatur. Für eine weiterführende Arbeit wäre es sinnvoll, eine Beispiel-Pipeline praktisch aufzubauen und zu untersuchen, wie sich SAST, DAST, SCA, Secret Scanning und Container Scanning konkret auf Laufzeit, Fehlalarme und Sicherheitsfunde auswirken.

---

[Zur Inhaltsübersicht](README.md) · [Vorheriges Kapitel](04-Ergebnisse-und-Bewertung.md) · [Zum Quellenverzeichnis](06-Literatur-und-Quellenverzeichnis.md)
