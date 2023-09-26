---
layout: default
title: "Was wird geprüft"
parent: "Home (German-Deutsch)"
nav_order: 5
description: "Was wird geprüft?"
has_children: false
---
---
layout: default
title: "Datenschutz"
parent: "Home (German-Deutsch)"
nav_order: 8
description: "Datenschutz"
has_children: false
---

Sie lesen die deutsche Übersetzung [dieser Seite](../scanning.md)

<h1>Was wird geprüft?</h1>
Im Folgenden wird beschrieben, was mit dem HCL Domino License Analysis Utility geprüft wird

<details close markdown="block">
  <summary>
    Inhalt
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

___
## Scan #1: HCL Domino Server Environment

Der erste Scan, der durchgeführt wird, betrifft die HCL Domino-Serverumgebung. Bei diesem Scan werden die folgenden Informationen über die HCL-Domino-Server gesammelt:

- Erkennung des Domino-Adminservers
- Namen aller Domino-Server
- Verfügbarkeit der Domino-Servers (Online oder Offline)
- Directory Assistance (DA)-Nutzung
  - Wenn DA in Gebrauch ist, werden alle zusätzlichen Domino-Verzeichnisse ermittelt.
- Prüfung auf gesicherte HTTP- und LDAP-Protokolle
- Erfassen der Namen der Deny Access Groups, die auf den Domino Servern verwendet werden
- Feststellen, ob Domino V12 verwendet wird, und wenn ja, auflisten, welche Domino-Server das Entitlement Tracking System verwenden
- Stellen Sie fest, ob das Domino-Lizenzverfolgungssystem läuft und auf welchen Domino-Servern

___
## Scan #2: HCL Domino Users

Der zweite Scan durchläuft alle Domino-Verzeichnisse und sammelt Informationen aus den gefundenen Personendokumenten.

Die aggregierten Informationen sind wie folgt:

- Name des Benutzers
- E-Mail Adresse des Benutzers
- Anmerkungen Ablaufdatum des Zertifikats (falls verfügbar)
- Angabe, ob das Internet-Passwort gesetzt ist (nicht das tatsächliche Internet-Passwort)
- Domino-Verzeichnis, in dem sich das Personendokument befindet
- Datum, an dem der Benutzer zuletzt auf einen Domino Server zugegriffen hat (nur wenn die Lizenzverfolgung aktiviert ist)
- Netzwerkprotokolle, die der Benutzer für den Zugriff auf die Domino-Server verwendet hat (nur wenn die Lizenzverfolgung aktiviert ist)

Bei den nachfolgenden Scans werden zusätzliche Informationen über jeden Benutzer gesammelt.

Bitte beachten Sie, dass alle diese Informationen nur lokal auf Ihrem Computer gespeichert werden. Für weitere Informationen siehe [Datenschutz](privacy.md)

___
## Scan #3: Deny Access Groups und Gruppenstruktur

Bei der dritten Überprüfung werden die auf dem Serverdokument gespeicherten Werte untersucht, um festzustellen, welche Zugriffsverweigerungsgruppen zur Sicherung der Domino-Server verwendet werden. 

Anhand der Liste der verwendeten Zugriffsverweigerungsgruppen ruft der Scan die Zugriffsverweigerungsgruppen und alle Mitglieder dieser Gruppen ab und stellt fest, ob es Gruppennamen innerhalb der Zugriffsverweigerungsgruppen gibt. Wenn zusätzliche Gruppennamen entdeckt werden, ruft der Scan auch die Informationen für diese zusätzlichen Gruppen ab. Dieses rekursive Scannen von Gruppen wird fortgesetzt, bis alle Gruppennamen verarbeitet worden sind.

Sobald all diese Informationen abgerufen wurden, werden alle Benutzer, die während des zweiten Scans entdeckt wurden, mit den Mitgliedern der gefundenen Zugriffsverweigerungsgruppen abgeglichen. Durch diesen Querverweis wird festgestellt, ob der Benutzer in einer Deny Access Group aufgeführt ist. Wenn der Name eines Benutzers gefunden wird, werden die Benutzerinformationen entsprechend aktualisiert.

___
## Scan #4: Entitlement Tracking / User Report Tool Ergebnisse

Bei der dritten Überprüfung wird eines von zwei verschiedenen Systemen untersucht:

1. Entitlement Tracking: Dies ist ein neues System, das in HCL Domino V12 eingeführt wurde. Wenn der Client HCL Domino V12 verwendet, wird dieser Scan immer durchgeführt.
2. User Report Tool Results: Hierbei handelt es sich um ein optionales System, das auf dem in HCL Domino V12 enthaltenen Entitlement Tracking-System basiert, aber rückwärtskompatibel zu Domino V9.x ist. Verwenden Sie [User Report Tool](https://support.hcltechsw.com/csm?id=kb_article&sysparm_article=KB0095328) _bevor_ Sie DLAU nutzen. 


Die Informationen, die dieser Scan abruft, zeigen die höchste Zugriffskontrolllistenstufe des Benutzers an, die jeder Benutzer in der HCL-Domino-Umgebung hat. Dies ist nützlich, um festzustellen, ob es sich bei dem Benutzer um einen CCB- oder CCX-Lizenzbenutzer handelt.