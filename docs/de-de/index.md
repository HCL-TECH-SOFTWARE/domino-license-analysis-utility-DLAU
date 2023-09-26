---
layout: default
title: "Home (German-Deutsch)"
nav_order: 2
description: "HCL Domino License Analysis Utility"
has_children: true
---

Sie lesen die deutsche Übersetzung [dieser Seite](../index.md)

[Neueste Version Herunterladen](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/releases/latest){: .btn .btn-green }
[Auf GitHub ansehen](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/){: .btn }

<h1>HCL Domino License Analysis Utility</h1>
Dieses Tool unterstützt Domino Administratoren bei der Durchführung eines Health Checks und der Ermittelung der Anzahl der Authorisierten Benutzer einer vorhandenen HCL Domino Umgebung gemäß des CCB & CCX Lizenzmodelles

<details close markdown="block">
  <summary>
    Inhalt
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Ziel

Ziel dieses Tools ist es schnell und zuverlässig die genaue Anzahl der autorisierten Benutzer einer HCL Domino Umgebung zu ermitteln welche ein Domino Administrator sonst manuell ermitteln müsste. 

DLAU automatisiert den Prozess der Berechung indem es die benötigten Informationen die zur Ermittelung der Benutzeranzahl erforderlich sind in kürzester Zeit einsammelt und lokal auswertet.

Weitere Informationen zum Lizenzmodell sind in diesem Blogpost verfügbar:
[All You Ever Wanted to Know About Domino CCB Licensing and DLAU Tool](https://blog.hcltechsw.com/domino/all-you-ever-wanted-to-know-about-domino-ccb-licensing-and-dlau-tool/?referrer=opensource.hcltechsw.com/domino-license-analysis-utility-DLAU/)

## Einleitung

{% include youtube.html id="zBPAdHMGzzo" %}


## Dokumentation
Erfahren Sie mehr über das HCL Domino License Analysis Utility in folgenden Artikeln:

* [Schritt für Schritt Anleitung](/de-de/instructions.md)
* [Ergebnisse verstehen](results.md)
* [Lizenzberechnung](licensecalc.md)
* [Was ist das Domino License Utility (PDF)](../../assets/pdf/what-Is-the-domino-license-analysis-utility.pdf)
* [Was wird gescannt](scanning.md)
* [Erklärung der Observations](observations.md)
* [Fragen und Antworten](faqs.md)
* [Einschränkungen](/de-de/limitations.md)

## Kompatibilität

Siehe [Systemanforderungen](requirements.md)

## Geschwindigkeit und Laufzeit

Abhängig von der Anzahl der Personendokumente in der HCL Domino Umgebung kann der Prozess von wenigen Minuten bis zu mehreren Stunden dauern, die folgende Tabelle spiegelt unsere Erfahrungen wieder:

Personendokumente | Laufzeit
--- | --- 
1.000 | 45 minuten
5,000 | 90 minuten
10 k | 2 Stunden
1 Millionen | 15 Stunden

## Änderungen

Das Tool wird regelmäßig aktualisiert - welche Änderungen in dieser Version vorgenommen worden sind lesen sie im [CHANGE LOG](../changelog.md)
