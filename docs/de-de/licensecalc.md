---
layout: default
title: "Lizenzberechnung"
parent: "Home (German-Deutsch)"
nav_order: 2
description: "Lizenzberechnung"
has_children: false
---

<h1>Wie CCB und CCX Lizenzen berechnet werden</h1>

<details close markdown="block">
  <summary>
    Inhalt
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

Es gibt zwei Lizenzmodelle für HCL Domino, die mit Hilfe von DLAU analysiert werden können, diese sind:

* Complete Collaboration Business Edition (CCB) 
-und-
* Complete Collaboration eXternal user (CCX)

## Complete Collaboration Business Edition (CCB) 

CCB Lizenzen sind für alle Mitarbeiter und Vertragsarbeiter des eigenen Unternehmens 
, wenn diese auf Domino Server Zugriff haben - damit sind alle B2E (Business-to-Employee) Scenarien gemeint. Alle CCB Benutzer können den kompletten Funktionsumfang von HCL Domino nutzen.

Zusätzlich enthält ein Server, welcher unter CCB Lizensiert ist, eine unbegrenzte Zahl von Nutzern für folgende B2C (Business-to-Consumer/Citizen)  Szenarien:

* Gäste: unbegrenzter Anonymer Zugriff via Browser um Domino-basierte Webseiten zu besuchen
* Bekannte Gäste: unbegrenter namentlicher Zugriff, d.h. Anmeldung am System mit höchstens Lesezugriff.

(Weitere Informationen zu diesem Lizenzmodell finden Sie unter [“Licensing Update: Domino V12 and Key CCX Enhancement”](https://blog.hcltechsw.com/domino/licensing-update-domino-v12-and-key-ccx-enhancement/)).

Die Menge der benötigten Lizenzen für eine CCB-Konfiguration entspricht der Menge aller im Domino Directory und aller angeschlossenen Authentifizierungsquellen in Ihrer gesamten Enterprise-Umgebung. 

## Complete Collaboration eXternal user (CCX)

Für B2B (Business-to-Business) oder speziellen B2C Szenarien be denen alle externen Benutzer mehr als nur Leserechte in Ihrer Umgebung benötigen, existiert diese zusätzliche Option. Complete Collaboration eXternal user (CCX) wird als Add-on zur CCB Lizensierung angeboten um z.B. ihren Business Partnern, externe Agenturen, etc eine Lizenz für den Zugriff auf Ihre Umgebung zu ermöglichen.

CCX Benutzer können den vollständigen Funktionsumfang der Domino und, sofern installiert, der Domino Leap Produktpalette nutzen um mit Anwendungen und Workflows zu arbeiten, aber sie können keine Anwendungen erstellen oder bearbeiten. CCX Benutzer dürfen auch kein eigenes Postfach haben, können allerdings Fach-/Funktionspostfächer für Workflows nutzen und aus Anwendungen heraus Mails erstellen.

Ähnlich wie das CCB Modell sind auch CCX als Authorisierte Benutzer zu betrachten, sind also namentlich bekannte Benutzer, werden jedoch nach 30 Tagen nichtbenutzung neu zugewisen. d.h. gezählt werden im CCX Modell nur Benutzer die sich innerhalb von 30 Tagen tatsächlich angemeldet haben. 

Beachten Sie in diesem Zusammenhang, Sie müssen genügend CCX Lizenzen vorhalten um die aktuelle und ggf zukünftige/schwankende Benutzermenge abzudecken.

Das CCX Lizenzmodell unterliegt einigen Einschränkungen, werden diese nicht erfüllt gilt ein Benutzer nicht als CCX sondern als CCB Benutzer. Die wichtigste Einschränkung für CCX Benutzer ist das dieser höchstens die Berechtigungsstufe "Editor" haben darf, d.h. ein CCX Benutzer kann Dokumente in einer Datenbank erstellen, und auch Dokumente anderer Benutzern editieren (dafür sind Editoren-Rechte erforderlich). Bisher waren nur Author-Rechte gestattet, seit Sept. 2024 dürfen CCX Benutzer auch Editor-Rechte erhalten.

Die Berechnung von CCB Lizenzen ist relativ einfach: Gezählt werden die Anzahl gültiger Personendokumente - gültig in diesem Fall heisst, daß es eine NotesID oder ein Kennwort zur Authentifizierung gibt, der Benutzername nicht in einer Deny-Access Gruppe aufgeführt ist, und der Benutzer mindestens zu einem Server der Umgebung Zugriff hat.

Die Berechnung von CCX Benutzern ist weitaus komplexer und erfordert zwei zustzliche Funktionen, die auf dem Domino Server bzw den Domino servern aktiviert sein müssen bevor der DLAU scan ausgeführt werden kann:

___

## Domino User License Tracking

Domino User License Tracking ist eine Funktion in Domino, die es seit Version 7 gibt. Es wurde entwickelt um dem Administrator einen Überblick darüber zu geben, welche Benutzer sich am System anmelden und über welche Protokolle (NRPC, HTTP, LDAP, SMTP, POP3, IMAP, IIOP) die Benutzer zugreifen.

Diese Informationen werden von DLAU benötigt um festzustellen wann ein Benutzer sich zuletzt angemeldet hat. Wie oben beschrieben ist diese Information wichtig um die Anzahl der benötigten CCX Lizenzen zu ermitteln.

CCX Lizenzen werden von DLAU als Höchstwert der Benutzer gezählt, die sich in den letzten 12 Monaten angemeldet haben. Für eine korrekte Berechnung ist es erforderlich das [Domino User License Tracking zu aktivieren](https://help.hcltechsw.com/domino/12.0.2/admin/conf_licensetracking_t.html) und die Informationen über den gesamten Zeitraum zu sammeln.

Zum Beispiel: 
Die Anzahl der CCX Benutzer schwankt im laufe eines Jahres wie in nachfolgender Tabelle dargestellt. DLAU wird den höchsten Wert innerhalb der letzten 12 Monate verwenden: 

- Jan:	12.000
- Feb:	11.000
- Mar:	10.000
- Apr:	10.500
- May:	12.500
- Jun:	14.000
- Jul:	13.500
- Aug:	12.000
- Sep:	13.000
- Oct:	14.000
- Nov:	12.500
- Dec:	11.000

d.h. in dieser Konfiguration würden 14.000 CCX Lizenzen benötigt werden.

Das User License Tracking System muß auf ALLEN(!) Domino Servern aktiviert werden, damit DLAU diese Informationen nutzen kann. Für weitere Informationen zur Akivierung lesen Sie bitte [License Tracking Enablement Instructions](https://help.hcltechsw.com/domino/12.0.2/admin/conf_licensetracking_t.html)

___

## Entitlement Tracking / Domino User Report Tool

Ein weiter wichtiger Aspekt zur richtigen Berechnung von CCX Benutzern ist das CCX Bentzer in der Zugriffskontrollliste von Datenbanken maximal nur Editor-Rechte haben dürfen - bezogen auf alle Domino Server und alle Datenbanken.

HCL hat für die Berechnung der Zugriffsrechte zwei Methoden bereitgestellt:

### für Server mit Domino 12.0 und höher
Seit Domino 12.0 gibt es eine integrierte Funktion namens “Entitlement Tracking"  welches die jeweils höchste Zugriffsberechtigung eines Benutzers über die gesamte Domino Domäne hinweg ausliest und tagesaktuell zur Verfügung stellt.

Wenn ein Benutzer mindestens Leserechte in der Umgebung besitzt wird er von dem System erfasst und im weiteren mit den jeweils höchsten Berechtigungen die in der Gesamten Umgebung existieren der Auswertung hinzufgefügt.

Das Entitlement Tracking ist in HCL Domino V12.0 enthalten und automatisch aktiviert.

### für Server mit Domino 11.0.x und kleiner

Ein ähnliches Tool namens "Domino User Report Tool" wurde speziell für Server entwickelt die nicht mit Version 12.0.x oder höher laufen. Es funktioniert ähnlich dem Entitlement Tracking nur erfolgt die Erfassung der Informationen über ein Tool welches auf einem Client PC und nicht auf dem Server gestartet wird. Das Ergebnis wird von DLAU für die weitere Berechnung der benötigten Lizenzen verwendet.

Das Domino User Report Tool wird als ausführbares Programm bereitgestellt und funktioniert mit Notes Client Versionen von V9.0.1 – V11.0.1.
Verfügbar ist das Tool als Download und wird vom Administrator der Umgebung ausgeführt.

Sie können das Tool über diesen Link herunterladen: [User Report Tool for gathering data on users' maximum access levels across a set of servers](https://support.hcltechsw.com/csm?id=kb_article&sysparm_article=KB0095328)

## Categorizing Users or Directories as 'External'

In order to identify if a user or account is an internal or external account, Directories and Person documents can be tagged. This tagging helps

### Adressbuch

Ein Adressbuch (Directory) welches nur(!) externe Benutzer enthält kann in der Directory Assistance datenbank als solches markiert werden.

Vorausssetzungen:
- Das Adressbuch muss in der Directory Assistance datenbank konfiguriert sein. 
- Directory Assistance Datenbank muss das Template (da.ntf) der Version v14.5 oder höher benutzen.

![Directory Assistance](../assets/images/png/categorize-directory.png)

Im Reiter 'Basics' des Directory Assistance Dokumentes, kann die Einstellung "Verzeichnis enthält externe Benutzer" auf "Ja" geändert werden um der License Administration-Funktion die Information zu übergeben das alle Benutzer in diesem Directory als externe Benutzer zu betrachten sind.

Das Feld wurde im Directory Assistance template (da.ntf) der version 14.5 einfgeführt. Das Template ist  kompatibel mit HCL Domino Version 12.0.x und höher.

Für weitere Informationen siehe:
[HCL License Dashboard: Background and first steps](https://help.hcl-software.com/domino/14.5.0/admin/admn_dla_first_steps.html)

### Personendokument

Ein Personendokument in einem Domino Directory can als externer User Account markiert werden.

Die entsprechende Einstellung findet sich im Reiter "Erweitert" innerhalb des Personendokuments.
Das Feld "Account Type" kann auf "External" gesetzt werden um der License Administration-Funktion  die Information zu übergeben das es sich bei diesem Benutzer um einen externen Benutzer handelt.

![Person Document](../assets/images/png/categorize-person.png)

Beachte:
Wenn die tatsächlichen Berechtigungen des Accounts über den Lizenzbeschränkungen für externe Benutzer liegen, dann wird ein Benutzer als 'Intern' gezählt auch wenn der Account-Typ im Personendokument auf 'Extern' steht.

Technische Details:

Feld | Details
--- | --- 
Field Name | $$PersonClassification
Data Type | Text
Field Flags | SUMMARY
Field Value | "0" (default) for Internal, "1" for External

Um das Feld programmatisch zu setzen, kann z.B. ein LotusScript Agent verwendet werden der das Feld für alle markierten Dokumente in einer Ansicht setzt:

```
Dim session As New NotesSession
Dim collection As NotesDocumentCollection

Set collection = session.CurrentDatabase.UnprocessedDocuments
Set PersonDoc = collection.GetFirstDocument()
While Not(PersonDoc Is Nothing)

  If not (PersonDoc.GetItemValue ("$$PersonClassification")(0) = "1") then
    Call PersonDoc.ReplaceItemValue ("$$PersonClassification","1")
    Call PersonDoc.Save (True,False)
  end if 

  Set doc = collection.GetNextDocument(PersonDoc)
Wend
```

Für weitere Informationen siehe: [Understanding the Person document](https://help.hcl-software.com/domino/14.5.0/admin/othr_persondocuments_r.html)
