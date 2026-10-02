# 2. Grundlagen und verwandte Arbeiten

### 2.1 Software Engineering und sichere Softwareentwicklung

Software Engineering beschäftigt sich mit der planvollen Entwicklung von Software. Dabei geht es nicht nur darum, Code zu schreiben. Wichtig sind auch Anforderungen, Entwurf, Tests, Wartung, Qualität und die Weiterentwicklung eines Systems. Sicherheit ist dabei ein wichtiger Teil der Qualität. Eine Anwendung kann fachlich funktionieren und trotzdem ein Risiko darstellen, wenn sie unsicher entwickelt wurde.

Sichere Softwareentwicklung bedeutet, dass Sicherheitsaspekte schon während der Entwicklung berücksichtigt werden. Dazu gehören zum Beispiel sichere Programmierregeln, Prüfung von Eingaben, Schutz von Zugangsdaten, sichere Konfigurationen und regelmäßige Sicherheitsprüfungen. NIST beschreibt im SSDF grundlegende sichere Entwicklungspraktiken, die in unterschiedliche Softwareentwicklungsprozesse integriert werden können (vgl. NIST, 2022).

Für diese Arbeit ist wichtig, dass Sicherheit nicht als einmalige Abschlussprüfung verstanden wird. Sicherheit soll Schritt für Schritt im Entwicklungsprozess auftauchen. Automatisierte Sicherheitstests passen dazu, weil sie regelmäßig ausgeführt werden können. Dadurch wird Sicherheit eher zu einem wiederholbaren Bestandteil des Software Engineering und weniger zu einer Einzelprüfung am Ende.

Trotzdem darf sichere Softwareentwicklung nicht nur auf Tools reduziert werden. Tools können Hinweise liefern, aber Menschen müssen die Ergebnisse bewerten. Ein Tool kann zum Beispiel eine Warnung ausgeben, aber das Team muss entscheiden, ob es sich wirklich um ein kritisches Problem handelt und wie es behoben werden soll.

Für die praktische Umsetzung liefern OWASP ASVS und OWASP SAMM zusätzliche Orientierung. ASVS beschreibt überprüfbare Sicherheitsanforderungen für Anwendungen, während SAMM Organisationen dabei unterstützt, ihren sicheren Entwicklungsprozess schrittweise weiterzuentwickeln (vgl. OWASP ASVS, o. J.; OWASP SAMM, o. J.).

### 2.2 DevOps

DevOps ist ein Ansatz, der Entwicklung und Betrieb näher zusammenbringt. In klassischen Projekten sind diese Bereiche oft getrennt. Entwicklerinnen und Entwickler erstellen die Software, während der Betrieb später für Bereitstellung, Betrieb und Wartung zuständig ist. Diese Trennung kann zu langsamen Übergaben, Missverständnissen und Fehlern führen.

DevOps versucht, diese Trennung zu verringern. Teams sollen enger zusammenarbeiten und Abläufe stärker automatisieren. Typische Bestandteile sind Versionsverwaltung, automatisierte Builds, automatisierte Tests und CI/CD-Pipelines. Dadurch können Änderungen schneller geprüft und bereitgestellt werden.

Für die Sicherheit entsteht dadurch aber eine neue Herausforderung. Wenn Software häufiger veröffentlicht wird, müssen auch Sicherheitsprüfungen häufiger und schneller stattfinden. Rein manuelle Sicherheitsprüfungen können mit dem Tempo von DevOps oft schwer mithalten. Deshalb wird DevOps in vielen Quellen durch DevSecOps erweitert (vgl. Myrbakken und Colomo-Palacios, 2017).

### 2.3 DevSecOps und Shift Left Security

DevSecOps steht für Development, Security und Operations. Der Begriff beschreibt eine Erweiterung von DevOps um den Sicherheitsaspekt. Sicherheit soll nicht erst nach der Entwicklung geprüft werden, sondern von Anfang an Teil des Entwicklungsprozesses sein. Dieser Gedanke wird häufig mit Shift Left Security verbunden. Gemeint ist, dass Sicherheitsprüfungen früher im Prozess stattfinden sollen.

Myrbakken und Colomo-Palacios beschreiben DevSecOps als Reaktion auf die Geschwindigkeit von DevOps. Traditionelle Sicherheitsmethoden passen oft nicht gut zu schnellen DevOps-Prozessen, weil sie zu spät oder zu langsam eingesetzt werden (vgl. Myrbakken und Colomo-Palacios, 2017). Neuere Literatur zeigt außerdem, dass DevSecOps mehrere Dimensionen umfasst, zum Beispiel Definitionen, Herausforderungen, Praktiken, Tools und Metriken (vgl. Zhao et al., 2024).

Rajapakse et al. zeigen in einer systematischen Übersicht, dass DevSecOps sowohl technische als auch organisatorische Herausforderungen hat. Sie ordnen Herausforderungen unter anderem den Bereichen Menschen, Praktiken, Tools und Infrastruktur zu (vgl. Rajapakse et al., 2022a). Das ist für diese Arbeit wichtig, weil automatisierte Sicherheitstests nur ein Teil von DevSecOps sind.

OWASP beschreibt DevSecOps als Ansatz, um sichere Pipelines zu entwickeln, passende Sicherheitswerkzeuge einzusetzen und Shift-Left-Security zu unterstützen (vgl. OWASP, o. J.-d). Für diese Arbeit bedeutet DevSecOps daher vor allem: Sicherheit wird automatisiert und wiederholbar in den CI/CD-Prozess eingebaut. Trotzdem ersetzt Automatisierung nicht das Denken und Bewerten durch Menschen.

### 2.4 CI/CD-Pipelines

CI/CD steht für Continuous Integration und Continuous Delivery beziehungsweise Continuous Deployment. Bei Continuous Integration werden Codeänderungen regelmäßig zusammengeführt und automatisch geprüft. Bei Continuous Delivery oder Deployment wird Software nach erfolgreichen Prüfungen vorbereitet oder direkt in eine Umgebung ausgeliefert.

Eine einfache Pipeline kann zum Beispiel aus Commit, Build, Tests, Security-Scans, Image-Freigabe und Deployment bestehen. In jeden dieser Schritte können Prüfungen eingebaut werden. Funktionale Tests prüfen, ob die Software fachlich funktioniert. Sicherheitstests prüfen zusätzlich, ob sicherheitsrelevante Probleme vorhanden sind. Dadurch eignen sich CI/CD-Pipelines besonders gut, um Sicherheitstests regelmäßig und nachvollziehbar auszuführen.

| Phase | Prüfungen / Aktivitäten |
| --- | --- |
| Commit / PR | Secret Scan; SAST |
| Build | SCA / Dependency Scan |
| Test | Unit-/Integration; SAST |
| Testumgebung | DAST / ZAP; Security Tests |
| Image / Release | Container Scan; Freigabe |
| Deployment | Monitoring; Review |

Abbildung 1: Vereinfachte DevSecOps-Pipeline mit typischen automatisierten Sicherheitstests.

Eigene Darstellung auf Basis der betrachteten Quellen.

Die Pipeline selbst muss ebenfalls geschützt werden. Sie hat häufig Zugriff auf Quellcode, Secrets, Build-Artefakte und Deployment-Systeme. OWASP weist darauf hin, dass CI/CD-Pipelines wegen ihrer Rolle im Software Development Life Cycle ein attraktives Ziel für Angriffe sein können und daher nicht ignoriert werden dürfen (vgl. OWASP, o. J.-b). Der OWASP Top 10 CI/CD Security Risks macht diesen Punkt ebenfalls deutlich, weil dort typische Risiken wie unsichere Pipeline-Konfigurationen, unzureichende Zugriffskontrolle und der Umgang mit Secrets als zentrale Themen genannt werden (vgl. OWASP, o. J.-c).

Auch die Software Supply Chain spielt hier eine Rolle. OWASP nennt als mögliche Bedrohungen unter anderem Dependency Confusion, manipulierte Build-Prozesse und unsichere Artefaktverwaltung; das Projekt „Top 10 CI/CD Security Risks“ ergänzt diese Sicht um typische Schwächen wie unsichere Pipeline-Konfigurationen oder zu weitgehende Berechtigungen (vgl. OWASP, o. J.-l; OWASP, o. J.-c). OpenSSF/SLSA bietet dazu ein Reifegradmodell, mit dem sich die Integrität von Build-Prozessen und Artefakten systematisch absichern lässt (vgl. OpenSSF/SLSA, o. J.).

### 2.5 Automatisierte Sicherheitstests

Automatisierte Sicherheitstests sind Prüfungen, die mit Werkzeugen automatisch ausgeführt werden. Sie können Quellcode, Abhängigkeiten, Container-Images oder eine laufende Anwendung prüfen. Der Vorteil besteht darin, dass solche Tests regelmäßig durchgeführt werden können. Dadurch werden Probleme früher sichtbar als bei einer einzelnen manuellen Prüfung am Ende.

Automatisierte Tests haben aber Grenzen. Sie finden nicht alle Schwachstellen und können Fehlalarme erzeugen. Deshalb müssen Ergebnisse bewertet und priorisiert werden. Ein Team muss entscheiden, welche Meldungen kritisch sind, welche nur dokumentiert werden und wann ein Build gestoppt wird. DevSecOps bedeutet deshalb nicht nur Tool-Einsatz, sondern auch klare Regeln und Verantwortlichkeiten.

#### 2.5.1 SAST

SAST bedeutet Static Application Security Testing. Dabei wird Quellcode oder ein anderer statischer Softwarebestandteil geprüft, ohne dass die Anwendung laufen muss. OWASP beschreibt Static Code Analysis als Analyse von nicht laufendem Quellcode, bei der Werkzeuge mögliche Schwachstellen und unsichere Muster erkennen sollen (vgl. OWASP, o. J.-m).

SAST eignet sich besonders früh im Entwicklungsprozess, zum Beispiel beim Commit, im Pull Request oder während des Builds. Der Vorteil ist, dass Entwicklerinnen und Entwickler Probleme direkt im Code sehen können. Ein Nachteil ist, dass SAST nicht immer erkennt, wie sich die Anwendung zur Laufzeit verhält. Außerdem können Fehlalarme entstehen, die geprüft werden müssen.

#### 2.5.2 DAST

DAST bedeutet Dynamic Application Security Testing. Dabei wird eine laufende Anwendung getestet. Das Tool prüft die Anwendung von außen, ähnlich wie ein Angreifer bestimmte Anfragen oder Eingaben testen würde. DAST wird deshalb eher nach dem Build oder in einer Testumgebung eingesetzt.

Ein bekanntes Werkzeug ist OWASP ZAP. Die ZAP-Dokumentation beschreibt ZAP als Werkzeug, das für Security Testing von Webanwendungen eingesetzt werden kann und auch Möglichkeiten zur Automatisierung bietet (vgl. OWASP ZAP, o. J.). Der Vorteil von DAST ist, dass die laufende Anwendung betrachtet wird. Der Nachteil ist, dass der Test später in der Pipeline stattfindet und teilweise länger dauern kann.

#### 2.5.3 Dependency Scanning und Software Composition Analysis

Dependency Scanning oder Software Composition Analysis prüft externe Bibliotheken und Komponenten. Das ist wichtig, weil moderne Anwendungen viele fremde Pakete verwenden. Eine Anwendung kann also auch dann unsicher sein, wenn der eigene Code sauber geschrieben ist, aber eine verwendete Bibliothek eine bekannte Schwachstelle enthält.

OWASP Dependency-Check ist ein Beispiel für ein SCA-Werkzeug. OWASP beschreibt es als Werkzeug, das Projektabhängigkeiten prüft und versucht, bekannte veröffentlichte Schwachstellen in diesen Abhängigkeiten zu erkennen (vgl. OWASP, o. J.-e). Solche Prüfungen passen gut in die Build-Phase, weil dort die verwendeten Abhängigkeiten sichtbar sind.

#### 2.5.4 Secret Scanning

Secret Scanning prüft, ob Zugangsdaten im Quellcode, in Konfigurationsdateien oder in der Repository-Historie enthalten sind. Dazu gehören zum Beispiel API-Keys, Tokens, Passwörter oder private Schlüssel. Solche Daten sollten nicht im Code gespeichert werden, weil sie bei Veröffentlichung missbraucht werden können.

GitHub beschreibt Secret Scanning als Prüfung der Repository-Historie auf hartcodierte Zugangsdaten wie API-Keys, Passwörter und Tokens (vgl. GitHub Docs, o. J.). Secret Scanning sollte möglichst früh stattfinden, zum Beispiel beim Commit oder Pull Request. Wird ein Secret erst spät gefunden, muss es oft zurückgezogen und neu erstellt werden. Deshalb reicht es nicht, nur zu scannen; es braucht zusätzlich ein gutes Secrets Management. OWASP betont beim Secrets Management unter anderem die zentrale Verwaltung, Rotation und Kontrolle von Geheimnissen (vgl. OWASP, o. J.-j).

#### 2.5.5 Container Scanning

Container Scanning prüft Container-Images auf bekannte Schwachstellen und unsichere Bestandteile. Das ist wichtig, wenn Anwendungen mit Docker oder ähnlichen Technologien ausgeliefert werden. Ein Container enthält nicht nur den eigenen Anwendungscode, sondern auch Pakete und Systembestandteile, die ebenfalls Schwachstellen enthalten können.

NIST beschreibt Container als portable, wiederverwendbare und automatisierbare Möglichkeit, Anwendungen zu verpacken und auszuführen, weist aber auch auf Sicherheitsrisiken und notwendige Gegenmaßnahmen hin (vgl. NIST, 2017). Container Scanning passt daher besonders gut in die Phase vor dem Deployment. Wenn ein Image kritische Schwachstellen enthält, sollte es nicht ungeprüft veröffentlicht werden.

Zusammenfassend lassen sich die Testarten nach ihrem Prüfgegenstand und ihrem typischen Einsatzzeitpunkt einordnen. SAST untersucht den Quellcode bereits beim Commit, Pull Request oder Build. DAST benötigt dagegen eine laufende Anwendung und wird deshalb meist in einer Testumgebung eingesetzt. Dependency Scanning prüft externe Bibliotheken während des Builds, Secret Scanning sucht möglichst früh im Repository nach Zugangsdaten und Container Scanning kontrolliert das fertige Image vor dem Deployment. Die genaue Bewertung ihrer Stärken, Grenzen und ihres Zusammenspiels erfolgt im Ergebniskapitel.

### 2.6 Verwandte Arbeiten und Einordnung

Die betrachtete Forschung zeigt, dass DevSecOps nicht nur ein technisches Thema ist. Myrbakken und Colomo-Palacios ordnen DevSecOps als Verbindung von DevOps und Sicherheitspraktiken ein (vgl. Myrbakken und Colomo-Palacios, 2017). Zhao et al. strukturieren das Forschungsfeld in Definitionen, Herausforderungen, Praktiken, Werkzeuge und Metriken und führen diese Bereiche in einem Lebenszyklusmodell zusammen (vgl. Zhao et al., 2024). Prates und Pereira identifizieren darüber hinaus 39 DevSecOps-Praktiken und ordnen unter anderem SAST, DAST, automatisierte Sicherheitstests, Continuous Monitoring, Threat Modeling und Zusammenarbeit den Kernpraktiken zu (vgl. Prates und Pereira, 2025).

Weitere Studien ergänzen diese übergeordnete Sicht. Rajapakse et al. ordnen Herausforderungen und Lösungen den Bereichen Menschen, Praktiken, Werkzeuge und Infrastruktur zu (vgl. Rajapakse et al., 2022a). Ihre empirische Untersuchung zur Zusammenarbeit bei Application Security Testing zeigt außerdem, dass unklare Rollen, fehlende gemeinsame Ziele und begrenzte Unterstützung durch Werkzeuge die Zusammenarbeit erschweren können (vgl. Rajapakse et al., 2022b). Kumar und Goyal schlagen mit ADOC ein Modell vor, das Sicherheitskontrollen an mehreren Kontrollpunkten eines automatisierten Workflows verankert (vgl. Kumar und Goyal, 2020). Feio et al. leiten aus Literatur und Fallstudie konkrete Security-Aktivitäten für die Phasen Plan, Code, Build, Test, Release, Deploy, Operate und Monitor ab (vgl. Feio et al., 2024).

Die Praxisquellen von OWASP und NIST ergänzen diese wissenschaftlichen Arbeiten. OWASP liefert konkrete Hinweise zu DevSecOps, CI/CD-Sicherheit, statischer Codeanalyse, Dependency-Checks und sicheren Anforderungen. NIST liefert mit dem SSDF einen Rahmen für sichere Softwareentwicklung und mit SP 800-190 Hinweise zur Containersicherheit. Für diese Arbeit ist die Kombination aus wissenschaftlichen und fachlichen Quellen sinnvoll, weil DevSecOps sowohl ein Forschungsthema als auch ein praktisches Thema ist.

Damit ergibt sich für die vorliegende Arbeit ein klarer Fokus: Es geht nicht nur darum, einzelne Tools aufzuzählen. Wichtiger ist die Frage, wie die verschiedenen Testarten gemeinsam in einer Pipeline wirken und welche Vorteile und Grenzen diese Arbeitsweise hat.

---

[Zur Inhaltsübersicht](README.md) · [Vorheriges Kapitel](01-Einleitung.md) · [Nächstes Kapitel](03-Methodik.md)
