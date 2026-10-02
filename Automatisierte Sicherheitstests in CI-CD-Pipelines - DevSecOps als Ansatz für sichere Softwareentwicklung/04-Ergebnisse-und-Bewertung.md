# 4. Ergebnisse und Bewertung

### 4.1 DevSecOps als Erweiterung von DevOps

Die Literatur zeigt übereinstimmend, dass DevSecOps DevOps nicht ersetzt, sondern dessen Grundidee erweitert. DevOps verbindet Entwicklung und Betrieb, automatisiert Abläufe und verkürzt den Weg von einer Codeänderung bis zur Bereitstellung. DevSecOps ergänzt diesen Ablauf um Sicherheitsanforderungen, automatisierte Kontrollen, gemeinsame Verantwortlichkeiten und Sicherheitsrückmeldungen über den gesamten Lebenszyklus (vgl. Myrbakken und Colomo-Palacios, 2017; Kumar und Goyal, 2020; Zhao et al., 2024).

Der Unterschied liegt deshalb nicht nur im zusätzlichen Begriff „Security“. Im klassischen DevOps kann Sicherheit weiterhin als eigener Prüfschritt vor einer Veröffentlichung behandelt werden. In DevSecOps werden dagegen bereits in der Planung Sicherheitsanforderungen und Bedrohungen betrachtet, während der Entwicklung Code und Secrets geprüft, im Build Abhängigkeiten und Artefakte kontrolliert, in der Testphase laufende Anwendungen untersucht und im Betrieb Sicherheitsereignisse überwacht werden (vgl. Feio et al., 2024; Prates und Pereira, 2025).

Damit verändert DevSecOps drei Bereiche gleichzeitig: den Prozess, weil Security-Aktivitäten in die Pipeline aufgenommen werden; die Verantwortung, weil Entwicklung, Betrieb und Security gemeinsam handeln; und die Automatisierung, weil wiederholbare Kontrollen direkt in CI/CD ausgeführt werden.

Im direkten Vergleich verfolgt DevOps vor allem das Ziel, Software schnell und zuverlässig bereitzustellen. DevSecOps behält dieses Ziel bei, ergänzt es aber um eine laufende Risikoreduktion. Neben Development und Operations wird Security als gemeinsame Verantwortung einbezogen. Sicherheitsprüfungen finden dadurch nicht nur kurz vor einer Veröffentlichung statt, sondern bereits von der Planung bis zum Betrieb (vgl. Kumar und Goyal, 2020; Rajapakse et al., 2022a; Zhao et al., 2024).

Auch die Automatisierung wird erweitert. Während DevOps vor allem Build, funktionale Tests und Deployment automatisiert, ergänzt DevSecOps unter anderem Security-Scans, Security Gates und Policy-Prüfungen. Das Feedback umfasst damit nicht nur Funktion, Qualität und Verfügbarkeit, sondern zusätzlich Schwachstellen, Risiken und sicherheitsbezogene Ereignisse. Im Betrieb kommen Security Monitoring und Incident Response hinzu. Erfolg wird deshalb nicht nur an Geschwindigkeit und Stabilität gemessen, sondern auch daran, ob Risiken früh erkannt und angemessen behandelt werden (vgl. Prates und Pereira, 2025; Feio et al., 2024).

| DevOps | DevSecOps |
| --- | --- |
| Gemeinsame Verantwortung für Entwicklung und Betrieb | Gemeinsame Verantwortung von Development, Security und Operations |
| Automatisierung von Build, Test und Deployment | Zusätzliche automatisierte Security-Kontrollen in der gesamten Pipeline |
| Schnelle und häufige Softwareauslieferung | Schnelle Auslieferung mit kontinuierlicher Sicherheitsrückmeldung |
| Sicherheit oft als separate oder spätere Prüfung | Sicherheitsanforderungen, Tests, Gates und Monitoring in jeder Phase |

Kernaussage: DevSecOps ersetzt DevOps nicht, sondern erweitert dessen Prozess, Rollen und Automatisierung um kontinuierliche Sicherheit.

Abbildung 2: Gegenüberstellung von DevOps und DevSecOps. Eigene Darstellung auf Grundlage von Kumar und Goyal (2020), Rajapakse et al. (2022a), Zhao et al. (2024) und Prates und Pereira (2025).

### 4.2 Einordnung der Sicherheitstests in CI/CD-Pipelines

Eine DevSecOps-Pipeline erweitert den klassischen Ablauf an mehreren konkreten Stellen. In der Planungsphase werden Sicherheitsanforderungen, Risiken und Bedrohungsmodelle festgelegt. In der Code-Phase folgen sichere Programmierrichtlinien, Code Reviews, SAST und Secret Scanning. Während des Builds werden Abhängigkeiten mit SCA geprüft; zusätzlich können Infrastructure-as-Code-Dateien und erzeugte Artefakte kontrolliert werden (vgl. Kumar und Goyal, 2020; Feio et al., 2024).

In der Testphase wird die gebaute oder laufende Anwendung untersucht. Hier passen DAST, Fuzzing und Integrationstests. Vor der Freigabe können Security Gates festlegen, ob kritische Funde einen Release stoppen. Beim Deployment werden Container-Images, Konfigurationen und Berechtigungen geprüft. Im Betrieb und Monitoring kommen Patching, Protokollauswertung, Schwachstellenüberwachung und Incident Response hinzu (vgl. Feio et al., 2024; Prates und Pereira, 2025).

Diese Einordnung zeigt, dass die fünf in dieser Arbeit genauer betrachteten Testarten nur einen Teil des Gesamtprozesses bilden. Sie werden durch organisatorische Regeln und weitere technische Kontrollen ergänzt. Abbildung 1 stellt diese Erweiterung über alle acht Phasen dar. Entscheidend ist, dass nicht überall derselbe Test wiederholt wird, sondern jede Phase eine zu ihrem Prüfobjekt passende Sicherheitsaktivität erhält.

Feio et al. zeigen in einer Fallstudie, dass die Umstellung einer vorhandenen DevOps-Pipeline konkrete Anpassungen an Phasen, Aktivitäten und Werkzeugen erfordert. Die Entwickler bewerteten die eingesetzten Werkzeuge grundsätzlich positiv, gleichzeitig blieben Aufwand, Fehlalarme und fehlende Expertise wichtige Grenzen (vgl. Feio et al., 2024). Damit wird DevSecOps als praktische Prozessänderung greifbar und nicht nur als allgemeine Forderung nach „mehr Sicherheit“.

### 4.3 Vergleich der Testarten

Der Vergleich der Testarten erfolgt nach den in der Methodik genannten Kriterien: Pipeline-Phase, Prüfobjekt, typische Funde, Stärken und Grenzen. Diese Kriterien passen zu der Forschung, die DevSecOps-Praktiken nicht nur nach Werkzeugnamen, sondern nach ihrer Rolle im Lebenszyklus einordnet (vgl. Zhao et al., 2024; Prates und Pereira, 2025; Feio et al., 2024). Dadurch wird klarer, dass die Testarten unterschiedliche Aufgaben haben und sich eher ergänzen, statt sich gegenseitig zu ersetzen.

Tabelle 1: Vergleich automatisierter Sicherheitstestarten in CI/CD-Pipelines. Eigene Darstellung auf Grundlage von NIST (2022), OWASP (o. J.-m), OWASP ZAP (o. J.), OWASP (o. J.-e), GitHub Docs (o. J.) und Souppaya et al. (2017).

| Testart | Typische Pipeline-Phase | Prüfobjekt | Typische Funde | Stärken | Grenzen |
| --- | --- | --- | --- | --- | --- |
| SAST | Commit, Pull Request, Build | Quellcode / statischer Code | Unsichere Muster, Codefehler, mögliche Schwachstellen | Sehr früh einsetzbar; Fundstelle im Code sichtbar | Erkennt Laufzeit- und Konfigurationsprobleme nur begrenzt; mögliche Fehlalarme |
| DAST | Testumgebung nach Build | Laufende Anwendung | Fehler im Verhalten der Anwendung, z. B. unsichere Eingaben | Prüft die Anwendung von außen im laufenden Zustand | Später in der Pipeline; kann mehr Zeit benötigen; Codeursache nicht immer direkt sichtbar |
| SCA / Dependency Scanning | Build / Dependency-Check | Externe Bibliotheken und Pakete | Bekannte CVEs in Abhängigkeiten | Wichtig für Software Supply Chain; gut automatisierbar | Abhängig von Datenbanken; Risiko muss trotzdem bewertet werden |
| Secret Scanning | Commit, Pull Request, Repository-Scan | Code, Konfiguration, Git-Historie | API-Keys, Tokens, Passwörter, private Schlüssel | Sehr frühe Erkennung kritischer Geheimnisse | Secrets müssen danach rotiert und sicher verwaltet werden |
| Container Scanning | Image / Release vor Deployment | Container-Image und enthaltene Pakete | Bekannte Schwachstellen in Image und Systempaketen | Wichtig vor Veröffentlichung von Images | Bewertet nicht automatisch Architektur oder Laufzeitkonfiguration |

Aus der Tabelle wird deutlich, dass kein einzelner Test alle Risiken abdeckt. SAST ist stark bei frühem Codefeedback, DAST ergänzt diese Sicht durch Tests an der laufenden Anwendung. Dependency Scanning und Container Scanning sind besonders wichtig für die Lieferkette, während Secret Scanning ein sehr konkretes Risiko im Repository adressiert. Für eine sichere Pipeline ist deshalb eine Kombination mehrerer Prüfungen sinnvoll.

Gleichzeitig muss das Team festlegen, welche Funde kritisch sind und wann ein Build gestoppt wird. Sonst besteht die Gefahr, dass zu viele Meldungen entstehen und wichtige Warnungen übersehen werden. Dieser Punkt verbindet die technische Ebene mit der organisatorischen Ebene von DevSecOps.

### 4.4 Vorteile von DevSecOps

Ein wichtiger Vorteil von DevSecOps ist die frühere Erkennung von Sicherheitsproblemen. Wenn Prüfungen bereits beim Commit, Pull Request oder Build ausgeführt werden, erhält das Team näher am Entstehungsort eine Rückmeldung. Rajapakse et al. nennen Shift Left und kontinuierliche Sicherheitsbewertung als zentrale Praktiken; Prates und Pereira ordnen SAST, DAST, automatisierte Sicherheitstests und Continuous Monitoring den Kernpraktiken von DevSecOps zu (vgl. Rajapakse et al., 2022a; Prates und Pereira, 2025).

Ein weiterer Vorteil ist die Regelmäßigkeit. Manuelle Sicherheitsprüfungen finden häufig nur zu bestimmten Zeitpunkten statt. Automatisierte Tests können dagegen bei jeder Änderung oder regelmäßig in der Pipeline laufen. OWASP beschreibt DevSecOps als Ansatz, um Sicherheitswerkzeuge in Pipelines einzubinden und eine Shift-Left-Kultur zu fördern (vgl. OWASP, o. J.-d).

DevSecOps kann außerdem die Zusammenarbeit verbessern. Entwicklung, Betrieb und Security müssen gemeinsame Regeln definieren. Das kann helfen, Sicherheit nicht als externe Kontrolle zu sehen, sondern als gemeinsame Aufgabe. Rajapakse et al. zeigen, dass Zusammenarbeit, klare Rollen und gemeinsame Ziele zentrale Punkte bei der Einführung von DevSecOps sind (vgl. Rajapakse et al., 2022a; Rajapakse et al., 2022b).

Ein weiterer Vorteil ist die bessere Nachvollziehbarkeit. Wenn Tests in der Pipeline laufen, entstehen Berichte und Ergebnisse. Diese können zeigen, welche Prüfungen durchgeführt wurden und welche Probleme gefunden wurden. Das kann auch für Qualitätssicherung, spätere Audits oder interne Dokumentation hilfreich sein.

### 4.5 Herausforderungen von DevSecOps

Trotz der Vorteile gibt es mehrere Herausforderungen. Eine große Herausforderung sind Fehlalarme und eine hohe Zahl an Meldungen. Wenn Ergebnisse nicht priorisiert werden, können wichtige Warnungen übersehen werden. In der Fallstudie von Feio et al. konnten Funde wegen fehlender Expertise und des hohen Volumens nicht vollständig bereinigt werden. Dies zeigt, dass Automatisierung ohne Triage und Fachwissen keine verlässliche Aussage über den tatsächlichen Sicherheitsstand liefert (vgl. Feio et al., 2024).

Eine weitere Herausforderung ist der Aufwand bei der Einführung. Eine bestehende Pipeline muss angepasst werden; Werkzeuge müssen ausgewählt, eingerichtet und gepflegt werden. Außerdem sind Regeln nötig, wann ein Fund einen Build stoppt. Akbar et al. priorisieren unter anderem fehlende sichere Coding-Standards, fehlende automatisierte Security-Tools und mangelndes Wissen über statische Sicherheitstests als besonders wichtige Herausforderungen (vgl. Akbar et al., 2022). Rajapakse et al. bestätigen, dass technische und organisatorische Probleme gemeinsam betrachtet werden müssen (vgl. Rajapakse et al., 2022a).

Auch fehlendes Security-Wissen kann ein Problem sein. Wenn ein Entwicklungsteam nicht versteht, was eine Meldung bedeutet, kann es schwierig sein, richtig zu reagieren. Automatisierte Tests liefern Hinweise, aber sie ersetzen keine fachliche Bewertung. Das passt auch zu OWASP Secure Code Review, weil automatisierte Tools dort eher als Unterstützung und nicht als Ersatz für menschliche Prüfung verstanden werden (vgl. OWASP, o. J.-k).

Ein weiteres Risiko besteht darin, sich zu stark auf Tools zu verlassen. DevSecOps bedeutet nicht, dass Sicherheit automatisch vollständig gelöst ist. Architekturentscheidungen, Rechtekonzepte, Bedrohungsmodelle und manuelle Reviews bleiben wichtig. Außerdem muss die CI/CD-Pipeline selbst geschützt werden, weil sie Zugriff auf Code, Secrets und Deployment-Systeme hat (vgl. OWASP, o. J.-b; OWASP, o. J.-c).

### 4.6 Übergeordnetes Ergebnis: DevSecOps als Gesamtsystem

Die Einzelergebnisse lassen sich zu einem übergeordneten Bild zusammenführen. DevSecOps ist ein sozio-technisches System, in dem vier Ebenen zusammenwirken: Menschen, Praktiken, Werkzeuge und Infrastruktur. Diese Einordnung lehnt sich an die systematische Übersicht von Rajapakse et al. an und wird durch das Lebenszyklusmodell von Zhao et al. ergänzt (vgl. Rajapakse et al., 2022a; Zhao et al., 2024).

Auf der Ebene der Menschen sind gemeinsame Verantwortung, klare Rollen und Security-Wissen entscheidend. Die Ebene der Praktiken umfasst unter anderem Shift Left, Threat Modeling, sichere Anforderungen, Security Gates und eine kontinuierliche Bewertung. Werkzeuge unterstützen diese Praktiken durch SAST, DAST, SCA, Secret Scanning, Container Scanning und Monitoring. Zur Infrastruktur gehören die CI/CD-Plattform, Build-Systeme, Secrets, Artefakte und Laufzeitumgebungen, die ebenfalls geschützt werden müssen (vgl. Kumar und Goyal, 2020; Prates und Pereira, 2025).

Das Zusammenspiel der vier Ebenen lässt sich folgendermaßen beschreiben: Im Mittelpunkt steht eine kontinuierliche und sichere Softwarelieferung von der Planung bis zum Monitoring. Die Menschen legen Verantwortlichkeiten fest, bringen Security-Wissen ein und bewerten die Ergebnisse der Tests. Die Praktiken geben vor, wie Sicherheit umgesetzt wird, zum Beispiel durch Shift Left, Threat Modeling, Security Gates und regelmäßige Bewertungen. Die Werkzeuge automatisieren konkrete Prüfungen wie SAST, DAST, SCA, Secret Scanning, Container Scanning und Monitoring. Die Infrastruktur stellt die technische Grundlage bereit und muss CI/CD-Systeme, Secrets, Artefakte und Laufzeitumgebungen schützen. Erst durch die Verbindung dieser vier Bereiche entsteht ein durchgängiger DevSecOps-Prozess. Ein einzelnes Tool reicht dafür nicht aus, weil Funde ohne klare Zuständigkeiten, passende Regeln und geschützte Systeme wirkungslos bleiben können.

Das zentrale Ergebnis der Literaturauswertung lautet daher: Automatisierte Sicherheitstests schaffen vor allem dann einen Nutzen, wenn sie an geeigneten Kontrollpunkten der Pipeline ausgeführt, durch klare Prozesse unterstützt und in einen kontinuierlichen Feedbackkreislauf eingebettet werden. DevSecOps ist damit nicht nur eine technische Erweiterung von DevOps, sondern ein Gesamtsystem aus Verantwortung, Sicherheitspraktiken, automatisierten Werkzeugen und geschützter Infrastruktur.

---

[Zur Inhaltsübersicht](README.md) · [Vorheriges Kapitel](03-Methodik.md) · [Nächstes Kapitel](05-Fazit.md)
