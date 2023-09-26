---
layout: default
title: "Ergebnisse verstehen"
parent: "Home (German-Deutsch)"
nav_order: 7
description: "Ergebnisse verstehen"
has_children: false
---

Sie lesen die deutsche Übersetzung [dieser Seite](../results.md)

<h1>Ergebnisse verstehen</h1>

<details close markdown="block">
  <summary>
    Inhalt
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

___
Sobald der Scan abgeschlossen ist wird Ihnen eine Übersicht der Ergebnisse angezeigt wie hier dargestellt::

![Scan Results](assets/images/png/14-scan-results.png)

Dies ist das Ergebnis der durchgeführten Scans. Was es bedeutet und wie die Informationen zu verstehen sind wird im nachfolgend beschrieben.

____
### Authorized Users
Der Wert "Autorisierte Benutzer" ist die Gesamtzahl der Benutzer, die autorisiert sind oder die Fähigkeit haben, auf Ihre HCL Domino-Server zuzugreifen. Die angezeigte Zahl wird von vielen Faktoren bestimmt:

1. Die Anzahl der Personendokumente, die in allen Domino-Verzeichnissen in Ihrer Umgebung enthalten sind
2. Diese Personendokumente haben ein gültiges Notenzertifikat
  - Wenn in dem Personendokument kein Notes-Zertifikat vorhanden ist, aber dennoch ein Internet-Passwort verfügbar
3. Der Name des Benutzers ist in keiner der Zugriffsverweigerungsgruppen aufgeführt, die auf den HCL-Domino-Servern verwendet werden.
4. Wenn der Benutzer in einer Zugriffsverweigerungsgruppe aufgeführt ist, kann der Benutzer immer noch als autorisierter Benutzer gezählt werden, wenn die HTTP- und/oder LDAP-Ports aktiviert sind, aber NICHT dieselben Sicherheitseinstellungen verwendet werden, die für den Rest der HCL Domino-Server verwendet wird. Weitere Informationen zu diesem Thema finden Sie in der [Observations Explained](../observations.md) page.

Die Anzahl der autorisierten Benutzer wird für Lizenzzwecke verwendet.

___
### CCB Benutzer
Der Wert "CCB-Benutzer" ist die Gesamtzahl der internen Mitarbeiter der Organisation, die die Möglichkeit haben, die Domino-Umgebung zu nutzen und darauf zuzugreifen.

Auszug aus der Lizenzvereinbarung:

*"Licensee must obtain separate, dedicated CCB entitlements for each Internal User. “Internal User” shall mean permanent or temporary or transient employee, or person paid for, or acting on behalf of Licensee’s Enterprise ("Licensee’s Enterprise" is Licensee and all Affiliates per
MLA §1.1) who is assigned A/U access to the Program in any manner directly or indirectly (for example: via a multiplexing program, device, or application server) through any means.
In addition, Licensee must obtain separate, dedicated CCB entitlements to assign A/U credentials to a specific task or role or other such entities."*

___
### CCX Benutzer
Der Wert "CCX-Benutzer" ist die Gesamtzahl der externen Benutzer der Organisation, die die Möglichkeit haben, Dokumente in der Domino-Umgebung zu erstellen und zu lesen.

Auszug aus der Lizenzvereinbarung:

*"Licensee must obtain separate, dedicated CCX entitlements for
each External User. An "External User" is a unique person not included in above Internal Users, who is assigned Authorized User access to the Program with restricted maximum level of Domino application access (ACL) as "AUTHOR". A CCX A/U entitlement is unique, but may be reassigned to another user after thirty (30) days of inactivity."*

___
### Personendokumente
Der Wert "Personendokumente" ist die Gesamtzahl der Personendokumente, die in allen Domino-Verzeichnissen innerhalb der HCL-Domino-Umgebung enthalten sind.

___
### Mail Benutzer
Der Wert "Mail Users" ist die Gesamtzahl der Benutzer, die für den Zugriff auf HCL Domino Mail konfiguriert sind. Dies ist auch ein wichtiger Wert bei der Bestimmung des erforderlichen Lizenztyps, wenn Sie nicht bereits für Complete Collaboration for Business (CCB)-Lizenzen lizenziert sind.

___
### Deny Access Gruppen
Der Wert "Deny Access Groups" ist die Anzahl der Deny Access Groups, die auf Ihren HCL Domino-Servern verwendet werden. Diese Zahl umfasst auch alle rekursiven Gruppen, die beim Auffinden der verwendeten Deny Access Groups entdeckt wurden.

___
### Administration Server
Dies ist der HCL-Domino-Administrationsserver, der als Grundlage für alle durchgeführten Scans verwendet wurde.

__
### Alle Domino Servers in der Umgebung
Dies ist eine Liste aller HCL-Domino-Server, die in der Umgebung konfiguriert sind. Sie basiert auf den Server-Dokumenten, die in allen gescannten Domino-Verzeichnissen gefunden wurden.

In dieser Liste wird auch angezeigt, ob der Server online (verfügbar) oder offline ist.

___
### Entitlement Tracking Enabled Servers
Für HCL Domino V12.x-Umgebungen wurde ein neues System mit der Bezeichnung "Entitlement Tracking" eingeführt. Diese Liste enthält alle HCL Domino-Server in der Umgebung, auf denen das System "Entitlement Tracking" läuft.

Weitere Informationen zum "Entitlement Tracking System" finden Sie unter [Entitlement Tracking System](https://help.hcltechsw.com/domino/12.0.0/admin/admn_entitlementtracking.html)

___
### User Report Tool 
Für HCL Domino Server V9 - V11.x gibt es ein System namens "User Report Tool". Dieses System entspricht dem "Entitlement Tracking System", ist aber für HCL Domino Versionen kleiner als V12.x ausgelegt.

Der angezeigte Wert ist der Ort, an dem sich die Ergebnisse des User Report Tools befinden.

Weitere Informationen über das "User Report Tool" finden Sie unter: [User Report Tool Knowledgebase document](https://support.hcltechsw.com/csm?id=kb_article&sysparm_article=KB0095328)

___
### Directory Assistance Information
Dieser Wert zeigt an, wo sich der Verzeichnisdienstkatalog in Ihrer HCL-Domino-Umgebung befindet.

Wenn das Auskunftssystem nicht in Gebrauch ist, wird diese Information nicht angezeigt.

___
### Weitere Domino Verzeichnisse
Dieser Wert listet alle zusätzlichen Domino-Verzeichnisse auf, die in Ihrer Organisation vorhanden sind.

Wenn der erste aufgelistete Wert in der Farbe Blau angezeigt wird, bedeutet dies, dass das aufgelistete Domino-Verzeichnis verwendet wird, um "Externe Benutzer" aufzulisten - Benutzer, die keine Mitarbeiter der Organisation sind, denen aber dennoch ein begrenzter Zugriff auf die HCL-Domino-Server gewährt wird.

Wenn das Auskunftssystem nicht in Gebrauch ist, wird diese Information nicht angezeigt.

___
### Anmerkungen
Die im Abschnitt "Observations" angezeigten Werte listen alle Ergebnisse auf, die während des Scanvorgangs entdeckt wurden.

Die Beobachtungen können von "Informational" (kleinere Punkte, die den Wert der gesammelten Daten verbessern können) über "Warnings" (Punkte, die in Ihrer HCL Domino-Umgebung ein Problem darstellen können) bis hin zu "Security" (Punkte, die die Sicherheit Ihrer HCL Domino-Umgebung beeinträchtigen und sich auf die Anzahl der "Authorized User" auswirken) reichen.

{: .notice } 
Bei Sicherheitsrelevante Ergebnisse ist es empfehlenswert, sich mit jedem dieser Punkte zu befassen und den Scan dann erneut durchzuführen. Auf diese Weise erhalten Sie eine bessere Darstellung der tatsächlichen autorisierten Benutzer.

Weitere Informationen zu den einzelnen möglichen Beobachtungen finden Sie unter [Anmerkungen](observations.md)