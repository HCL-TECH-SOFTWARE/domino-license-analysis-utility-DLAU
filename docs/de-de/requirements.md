---
layout: default
title: "Voraussetzungen"
parent: "Home (German-Deutsch)"
nav_order: 1
description: "Systemanforderungen"
has_children: false
---

<h1>Systemanforderungen</h1>
Die folgenden Voraussetzungen müssen erfüllt sein, um das Programm ausführen zu können.

<details close markdown="block">
  <summary>
    Inhalt
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## Software

- Windows 7 oder höher
- Notes Client Version 7.0.2 oder höher
- Domino Server Version 7.0 oder höher

## Zugriffsrechte

- READ-Zugriff auf das Domino-Verzeichnis und andere Systemdatenbanken
- ACL-Rolle "[DenyAccessRead]" im Domino-Verzeichnis
- Gruppenmitgliedschaft in der Gruppe "LocalDomainAdmins".

## JavaScript-Unterstützung in den Notes-Client-Voreinstellungen

DLAU verwendet JavaScript für einige der internen Abläufe, deshalb ist es notwendig die Ausführung von JavaScript im Notes Client zu gestatten. Wenn die Verwendung von JavaScript im Notes Client nicht aktiviert ist wird DLAU nicht funktionieren.

JavaScript kann im Notes Client wie folgt aktiviert werden:
Im Notes Client, wählen Sie im Menü "Datei" den Punkt "Einstellungen" und aktivieren die folgenden drei (3) Optionen:

![Preferences](assets/images/png/notes-preferences.png)


## Weitere Anforderungen für CCX/Known Guest Berechnung

Um CCX und Bekannte Gäste in einer Domino-Umgebung richtig berechnen zu können, müssen zusätzliche Informationen an DLAU zur Analyse übermittelt werden.Für CCX-Benutzer gelten bestimmte Regeln, die beachtet werden müssen. Insbesondere darf ein CCX-Benutzer nur eine maximale Zugriffskontrolllistenstufe von "Autor" für alle Domino-Anwendungen haben. DLAU verwendet auch Informationen über die letzte erfolgreiche Anmeldung des CCX-Benutzers bei einem Domino-Server, um zu berechnen, ob der CCX-Benutzer aktiv oder inaktiv ist.

In ähnlicher Weise darf ein Bekannter Gast nur eine maximale Zugriffskontrolllistenstufe von "Leser" für alle Domino-Anwendungen haben.

Um die Informationen bereitzustellen, die DLAU für diese Berechnungen benötigt, müssen zwei zusätzliche Systeme in Ihrer Domino-Serverumgebung laufen:

* Lizenzverfolgungssystem: Dieses System ist seit Version 7.0 in Domino integriert und erfasst das Datum, die Uhrzeit und das Protokoll, das verwendet wurde, wenn sich ein Benutzer bei Domino authentifiziert.
 
[License Tracking System Konfigurationsanleitung](https://help.hcltechsw.com/domino/9.0.1/admin/admin/conf_licensetracking_t.html)

* Entitlement Tracking (wenn Domino V12) oder die Ergebnisse des User Report Tools: Diese Systeme versorgen DLAU mit der höchsten Zugriffskontrolllistenstufe jedes Domino-Benutzers. Dies ist nur wichtig, wenn der Client über externe Benutzer (CCX-Lizenzen) verfügt.

[Weitere Informationen](https://opensource.hcltechsw.com/domino-license-analysis-utility-DLAU/instructions/#schritt-6---entitlement-tracking--user-report-tool-scan)
