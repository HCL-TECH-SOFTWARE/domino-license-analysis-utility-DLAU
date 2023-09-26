---
layout: default
title: "Anmerkungen"
parent: "Home (German-Deutsch)"
nav_order: 6
description: "Anmerkungen"
has_children: false
---

Sie lesen die deutsche Übersetzung [dieser Seite](../issues.md)

<h1>Erklärung der Anmerkungen</h1>

<details close markdown="block">
  <summary>
    Inhalt
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
Während des Scanvorgangs wird eine Reihe von Beobachtungen erfasst. Diese können von einfachen Informationsbeobachtungen bis hin zu schwerwiegenderen potenziellen Sicherheitsschwachstellen in der HCL-Domino-Umgebung reichen.

Diese Beobachtungen werden während der Scans erfasst und dem Benutzer zur Verfügung gestellt, sobald alle Scans abgeschlossen sind.

Anweisungen zur Korrektur der HCL Domino-Umgebungseinstellungen, um die Beobachtungen zu korrigieren, werden innerhalb der DLAU-Schnittstelle bereitgestellt.

Nachfolgend finden Sie eine Liste der erfassten Beobachtungen mit einer Beschreibung, was die Beobachtung bedeutet.

**Hinweis:** Informationen in **_fett / kursiv_** sind nur als Beispiel zu verstehen.

___
## Security Observations

Der HCL Domino Server **_"Production/ACME"_** ist nicht ordnungsgemäß für HTTP-Verkehr gesichert

- Diese Beobachtung deutet darauf hin, dass die Serverzugriffseinstellungen für den HTTP-Verkehr nicht erzwungen werden. Wenn dies der Fall ist, kann der Benutzer mit einem Webbrowser auf die HCL Domino-Server zugreifen, selbst wenn der Name des Benutzers in einer Zugriffsverweigerungsgruppe aufgeführt ist. Der HTTP-Port muss ordnungsgemäß gesichert sein, damit Benutzer, die in einer Zugriffsverweigerungsgruppe aufgeführt sind, ordnungsgemäß gemeldet werden können, andernfalls werden sie als autorisierte Benutzer gezählt.

Der HCL Domino Server **_"Production/ACME"_** ist nicht ordnungsgemäß für den LDAP-Datenverkehr gesichert

- Diese Beobachtung deutet darauf hin, dass die Serverzugriffseinstellungen für den LDAP-Verkehr nicht erzwungen werden. Wenn dies der Fall ist, kann der Benutzer mit einem LDAP-Client auf die HCL Domino-Server zugreifen, selbst wenn der Name des Benutzers in einer Zugriffsverweigerungsgruppe aufgeführt ist. Der LDAP-Port muss ordnungsgemäß gesichert sein, damit Benutzer, die in einer Zugriffsverweigerungsgruppe aufgeführt sind, ordnungsgemäß gemeldet werden können, da sie sonst als autorisierte Benutzer gezählt werden.

Der HCL Domino Server **_"Production/ACME"_** verwendet keine Deny Access Groups zur Sicherung des Serverzugriffs

- Diese Beobachtung meldet, dass auf dem angegebenen HCL-Domino-Serverdokument keine Deny Access Group aufgeführt ist. Daher kann jeder, der über eine Notes-ID oder Internet-Zugangsdaten verfügt, auf den HCL-Domino-Server zugreifen. Selbst wenn ein Mitarbeiter das Unternehmen des Kunden verlässt, hat er immer noch die Möglichkeit, auf die HCL Domino-Umgebung zuzugreifen.
 
Die Deny Access-Gruppe mit dem Namen **_"ACME Deny Access"_** scheint in Ihrem Domino-Verzeichnis zu fehlen

- Diese Beobachtung zeigt an, dass die Gruppe "Deny Access" nicht existiert, obwohl sie im Domino-Server-Dokument aufgeführt ist. In diesem Szenario wird die Verwendung der Zugriffsverweigerungsgruppe ignoriert, und im Gegenzug hat jeder mit Anmeldeinformationen für die HCL-Domino-Umgebung Zugriff auf den HCL-Domino-Server.

___
## Warnungen 

Der HCL Domino Server **_"International/ACME"_** scheint offline zu sein

- Diese Beobachtung zeigt an, dass der aufgelistete Server während der Überprüfung der HCL-Domino-Umgebung nicht erreichbar ist. Dies kann entweder auf ein Konnektivitätsproblem hinweisen oder darauf, dass der HCL Domino-Server tatsächlich offline ist. Wenn der HCL Domino-Server absichtlich offline ist, kann der Benutzer nichts weiter tun. Wenn der aufgelistete HCL Domino-Server jedoch zugänglich sein sollte, weist diese Beobachtung auf ein potenzielles Konnektivitätsproblem für alle Benutzer hin.

Das in der Verzeichnisunterstützung konfigurierte HCL Domino-Verzeichnis kann nicht gefunden werden - Server: **_Production/ACME_** (Dateiname: **_external_names.nsf_**)

- Diese Anmerkung zeigt an, dass das aufgelistete zusätzliche Domino-Verzeichnis, das im Verzeichnisdienstkatalog konfiguriert ist, nicht zugänglich und/oder verfügbar ist. Diese Beobachtung kann zu Konnektivitäts- oder anderen Problemen für die Benutzer führen, die in dem zusätzlichen Domino-Verzeichnis aufgeführt sind.

Die Directory Assistance-Konfiguration **_"DomainName" (DomainTitle)_** ist ein LDAP-Verzeichnis

- Diese Beobachtung zeigt an, dass die HCL-Domino-Umgebung über eine Directory Assistance-Konfiguration verfügt, die eine Verbindung zu einem LDAP-Verzeichnis herstellt. Das Scannen von LDAP-Verzeichnissen wird von diesem Dienstprogramm noch nicht unterstützt. Daher ist die Gesamtzahl der angezeigten autorisierten Benutzer möglicherweise nicht repräsentativ für die Gesamtzahl der möglichen autorisierten Benutzer in Ihrer Umgebung.

___
## Informationelle Beobachtungen

Die Lizenzverfolgungsaufgabe läuft nicht auf dem HCL Domino-Server **_Production/ACME_**

- Diese Beobachtung zeigt an, dass auf dem aufgeführten HCL-Domino-Server das Domino-Lizenzverfolgungssystem nicht ausgeführt wird. Da es sich um ein optionales System handelt, besteht für den Domino-Administrator keine unmittelbare Notwendigkeit, irgendwelche Änderungen vorzunehmen. Wenn das Domino-Lizenzverfolgungssystem jedoch läuft, erhält der Domino-Administrator bessere Ergebnisse, wenn er die aggregierten Benutzerinformationen überprüft.

Die Zugriffsverweigerungsgruppe mit dem Namen **_"ACME More Deny Access"_** hat keine Mitglieder aufgelistet.

- Diese Beobachtung zeigt an, dass die in der HCL-Domino-Umgebung verwendete Deny Access-Gruppe keine Benutzernamen in ihrer Mitgliederliste hat. Es handelt sich um eine Informationsbeobachtung, da in der Mitgliederliste auch andere Gruppennamen aufgeführt sein können.