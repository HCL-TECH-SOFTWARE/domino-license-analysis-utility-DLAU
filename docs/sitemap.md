---
layout: default
title: "Sitemap"
nav_exclude: true
has_children: false
---

<h1>Sitemap</h1>

Just an overview of the navigation on this site

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

--- 

## Site Structure

```
+-- ..
|-- (Jekyll files)
|
|-- docs
|   |-- _includes           (Jekyll includes)
|   |
|   |-- assets              (images and other assets used on any page)
|   |   |-- images
|   |   |   |-- png
|   |   |   |-- svg
|   |   +-- pdf
|   |
|   |-- plantuml
|   |
|   |-- de-de               (Translated to German/de-de)
|   |   |-- index.md            (parent page for GERMAN)
|   |   |-- faq.md              (Fragen & Antworten)
|   |   |-- indstructions.md    (Schritt für Schritt Anleitung)
|   |   |-- issues.md           (Fehler melden)
|   |   |-- licensecalc.md      (Lizenzberechnung)
|   |   |-- limitations.md      (Bekannte Einschränkungen)
|   |   |-- oberservations.md   (Anmerkungen)
|   |   |-- privacy.md          (Datenschutz)
|   |   |-- results.md          (Ergebnisse verstehen)
|   |   +-- scanning.md         (Was wird geprüft)
|   |
|   |-- index.md      (parent page)
|   +-- ..            (other md files, pages with no children)
|
|-- (Jekyll files)
+-- ..

```