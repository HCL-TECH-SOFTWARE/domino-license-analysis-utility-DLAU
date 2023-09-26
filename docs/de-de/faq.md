---
layout: default
title: "Fragen & Antworten"
nav_order: 9
description: "Fragen und Antworten"
parent: "Home (German-Deutsch)"
has_children: false
---

Sie lesen die deutsche Übersetzung [dieser Seite](../faq.md)

<h1>Fragen und Antworten</h1>

<details open markdown="block">
  <summary>
    Inhalt
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

### Muss ich die Konfiguration meiner HCL Domino-Server ändern?
Nein. Dieses Dienstprogramm erfordert keine zusätzlichen Funktionen auf irgendwelchen HCL Domino-Servern. Es läuft vollständig auf dem lokalen Laufwerk des HCL Domino-Administrators, der das Dienstprogramm ausführt. Damit das Tool ordnungsgemäß funktioniert, muss Ihre Umgebung mit den [Systemanforderungen](requirements.md) übereinstimmen.

---

### Handelt es sich um eine Lizenzierungsprüfung? Muss ich unser(e) Rechts-/Compliance-Team(s) einbeziehen?
Es ist wichtig zu wissen, dass DLAU kein Lizenz-Audit durchführt, bei dem es sich immer um eine eingehende Analyse im Nachhinein handelt. Stattdessen erstellt das DLAU eine Baseline, die Ihnen und HCLSoftware hilft, ein sinnvolles, zukunftsorientiertes Gespräch für Ihre Erneuerung oder Ihren Neustart oder den Wechsel zu CCB oder Volt MX Go zu führen. Die Baseline muss vom Kunden im Hinblick auf zukünftige Einsatzpläne ergänzt werden, da der Kunde kontinuierlich für die Einhaltung der Lizenzbestimmungen verantwortlich ist.

---

### Wird der Prozess meinen Notes Client blockieren?
Die Scans innerhalb des Dienstprogramms laufen in einer Hintergrundaufgabe. Der Notes-Client des Benutzers kann während des Scanvorgangs wie gewohnt verwendet werden. Der Benutzer muss nur regelmäßig "einchecken", um zu sehen, ob der aktuelle Scan abgeschlossen ist und um zum nächsten Scan überzugehen.

---

### Wie lange wird der Prozess dauern?
Je nach Anzahl der Personendokumente und HCL-Domino-Server in der Umgebung sollte es 1 bis 3+ Stunden dauern. In einer kleinen Umgebung (~200 Benutzer) dauert der Scan ca. 45 Minuten, bei mittelgroßen Umgebungen (~5000 Benutzer) sollte ein Scann weniger als 2 Stunden dauern. 

Weitere Informationen darüber, wie lange der Prozess dauern kann, finden Sie auf der [Homepage](index.md#geschwindigkeit-und-laufzeit) dieses Projekts

---

### Wie kann ich die benötigten Berechtigungen nachweisen?
Auf der Seite "Scan-Ergebnisse" gibt es eine Schaltfläche mit der Bezeichnung "Druckfähiges Ergebnis anzeigen". Wenn Sie auf diese Schaltfläche klicken, erhalten Sie einen druckbaren Bericht, den Sie HCL als PDF (Print to PDF) zur Verfügung stellen können, falls Sie ihn für Verlängerungsgespräche benötigen. Die in diesem PDF enthaltenen Daten stehen im Einklang mit unserer [Datenschutzerklärung](privacy.md)

---

### Wie genau sind die Ergebnisse der Scans?
Obwohl es sich nicht um ein Audit-Tool handelt, liefert es in der Regel genaue Informationen über Ihre aktuelle Umgebung. Wenn Sie Zweifel haben, dass der Bericht nicht korrekt ist, wenden Sie sich bitte an Ihren HCL-Vertreter oder [report an issue](issues.md).  

Statistisch gesehen berichten Kunden von einer Genauigkeit von 96 %. Bei den 4 % handelt es sich im Allgemeinen um Sonderfälle wie spezielle Verwaltungs- oder Design Signing-Benutzer. 

Fügen Sie eine neue FAQ über CCB-/CCX-Berechnungen hinzu und verlinken Sie dann auf den Blogbeitrag vom 29. Juni

---

### Was ist der Unterschied zwischen CCB- und CCX-Lizenzen?
Weitere Informationen zu den Unterschieden zwischen CCB- und CCX-Lizenzen finden Sie in dem HCL Blog Post: 

[Alles, was Sie schon immer über die CCB-Lizenzierung von Domino und das DLAU-Tool wissen wollten](https://blog.hcltechsw.com/domino/all-you-ever-wanted-to-know-about-domino-ccb-licensing-and-dlau-tool/?referrer=opensource.hcltechsw.com/domino-license-analysis-utility-DLAU/)