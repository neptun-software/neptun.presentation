---
layout: default
---

# ERD

<div class="w-full h-full flex flex-col justify-center">
  <ul>
    <li>Benutzerverwaltung</li>
    <li>Chat-Funktionalität</li>
    <li>GitHub-Integration</li>
    <li>Projektverwaltung</li>
    <li>Datei- und Vorlagenverwaltung</li>
  </ul>

  <img
    src="https://raw.githubusercontent.com/neptun-software/neptun.web/refs/heads/main/backup/schema/schema.png"
    style="object-fit: contain;"
  />
</div>

<!--
Die implementierte REST-API-Architektur folgt dem Ressourcen-orientierten Paradigma
nach dem Richardson Maturity Model [1] und erreicht dabei Level 2. Diese
Implementierung ermöglicht standardisierte CRUD-Operationen auf sämtlichen persistierten
Datenentitäten des Systems durch korrekte Anwendung der HTTP-Methoden.
Die HTTP-Verben werden gemäß RFC 7231 semantisch korrekt eingesetzt und sämtliche
Ressourcen über URIs eindeutig adressierbar gemacht. Die API-Schnittstelle umfasst
funktional separierte Endpunkte für:

* AI-Modell-Interaktionen: Bereitstellung von einer generischen Schnittstelle für die
Kommunikation mit den integrierten Sprachmodellen
* Utility-Funktionen: Konvertierungsmodule für URL-zu-Markdown-Transformationen
und ähnliche Datenverarbeitungsfunktionen
* Benutzerverwaltung: Authentifizierung, Autorisierung und Profilmanagement
* Chat-Operationen: Persistenz und Verwaltung von Konversationsverläufen und
deren Metadaten sowie der Teilung von Chat-Konversationen
* Import-Funktionalität: GitHub-Schnittstellen mit GitHub-App-basierter Repository-
Anbindung
* Projektverwaltung: Manipulation von Projektmetadaten, Abhängigkeiten und
Konfigurationsparametern
* Dateiverwaltung: Speicherung, Modifikation und Retrieving von Konfigurationsdateien
* Template-Management: Erstellung, Modifikation und Teilung von Konfigurationsvorlagen

Die GitHub-Integrationsfunktionalität basiert auf einer registrierten GitHub-Applikation,
die mittels entsprechender Berechtigungsscopes Zugriff auf private Repositories gewährt.
Diese ermöglicht die Importierung von Konfigurationen. Die extrahierten Konfigurationen
dienen gemeinsam mit allen anderen Resourcen im Projekt als Kontext für die
Generierung domänenspezifischer Konfigurationsvorschläge.
-->
