---
layout: default
title: "Einschränkungen"
parent: "Home (German-Deutsch)"
nav_order: 3
description: "Bekannte Einschränkungen"
has_children: false
---

Sie lesen die deutsche Übersetzung [dieser Seite](../limitations.md)

<h1>Bekannte Einschränkungen</h1>

Anbei eine Liste bekannter Einschränkungen im Bezug auf DLAU. 

<details open markdown="block">
  <summary>
    Inhalt
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

___
## LDAP/ActiveDirectory 

Coming soon
{: .label .label-yellow }

Wenn der HCL Domino Server ein externes LDAP/Active Directory zur Authentifizerung von Web-Benutzern verwendet, kann DLAU nicht verifizieren welche Benutzer in diesem externen LDAP enthalten sind.

Deshalb ist in diesem Fall u.U. eine manuelle Prüfung notwendig.

{: .highlight } 
Aktuell arbeiten wir daran ebenfalls die LDAP / AD Verzeichnisse zu verarbeiten und mit den im License Tracking gefundenen Benutzerlisten abzugleichen.

___
## Mehrere/nicht verbundene Verzeichnisse

In HCL Domino Umgebungen welche in mehrere eigenständige Domänen aufgeteilt sind bzw. in denen die Directories(Adressbücher) nicht direkt über Directory Assistance eingebunden sind wird DLAU nur die Domino Domäne analysieren die im Arbeitsumgebungsdokument ihres HCL Notes Clients definiert wurde.

Um alle Domänen zu analysieren erstellen Sie bitte entsprechende Arbeitsumgebungsdokumente, d.h. eins pro Domäne und verwenden den jeweiligen Administrationsserver dieser Domäne jeweils als "Home/Mail Server".

Pro Domino Domäne erstellen Sie bitte einen eigenen DLAU report, d.h. verwenden eine DLAU Instanz pro Domäne. Nur so ist es möglich die in den einzelnen Domänen gesammelten Informationen später (manuell) zusammenzuführen. 

Bislang ist dieser Deduplizierungsprozess (leider noch) manuell durchzuführen, um sicherzustellen, daß jeder aufgeführte Benutzer in Ihren Domino Domänen nur einmal gezählt wird.

{: .note }
Wir arbeiten an einer Lösung die autom. Scanns auch über Domänengrenzen hinweg ermöglicht und auch mehrere Administrationsserver unterstützt.

___
## Directory Assistance auf anderen Servern als dem Administrationserver

DLAU wird nur dann nach zusätzlichen Adressbüchern/Domino Directories suchen wenn wenigstens der Domino Administrationsserver mit einer Directory Assistance DB (DA) konfiguriert wurde.

Falls in Ihrer Umgebung der Adminserver tatsächlich keine Directory Assistance (DA) DB nutzen, aber ein oder mehrere Server der gleichen Domino Domäne hingegen weitere Adressbücher über DA nutzen, so wird DLAU in der aktuellen Version diese zusätzlichen Adressbücher nicht verarbeiten.

{: .highlight } 
Note: Es handelt sich um eine bekannte Einschränkung an deren Behebung wir bereits arbeiten. Wir planen jeden Server auf die Verwendung von Directory Assistance zu prüfen.