---
title: "Konzepte"
linkTitle: "Konzepte"
weight: 4
bibFile: content/de/docs/Concepts/bib.json # path relative to project root
description: >
  Was muss der Benutzer über die Basiskonzepte Wissen ? 
---
{{ $simpleciteStyle := resources.Get "scss/hugo-simplecite.scss" | resources.ToCSS | resources.Minify | resources.Fingerprint }}
<link rel="stylesheet" type="text/css" href="{{ $simpleciteStyle.Permalink }}">

{{% pageinfo %}}
This is a placeholder page that shows you how to use this template site.
{{% /pageinfo %}}



# ICM
## Mehrbenutzer System

ICM ist ein Mehrbenutzersystem. Das bedeutet, das mehrere Benutzer an der Dokumentation eines Patienten zur gleichen Zeit mitwirken können.

## Mandanten
In ICM gibt es mehrere Mandanten, die im ursprünglichen Kontext einer Station entsprechen. Deshalb gibt es schon seit über 20 Jahren für jede der Intensivstationen einen Mandanten. 
Durch die Einführungvon ICM in der Anästhesie gibt es zusätzlich noch den Prämedikations- und den Anästhesie-Mandanten.

{{< alert >}}Ein Patient kann zueinem bestimmten Zeitpunkt immer nur in einem Mnadanten aufgenommen sein{{< /alert >}}

Eine Ausnahme ist die Anästhesie während eines ITS-Aufenthalts: ist ein Patient, der operiert werden soll, bereits auf einer der Intensivstationen aufgenommen, wird dieser nur temporär in den OP verlergt. Er ist also praktisch während der OP in beiden Mandanten.

# Integrationin die bestehende Krankenhaus IT

## Empfangen von Daten aus anderen Systemen
ICM kann folgende Daten aus der Klinik IT empfangen:
* Aufnahme Daten aus ORBIS
* Labor, dass während der jeweiligen Aufnahme in ICM abgenommen wurde
* Monitoring Daten aus dem Philips-Monitoring während der Liegedauer in einem ICM Bett mit Monitoring (Sonderfälle: Backfilling)

ICM kann folgende Daten **nicht** empfangen:
* OP-Anmeldung aus ORBIS
* Medikation aus ORBIS
* Befunde aus ORBIS
* Aufklärung aus Thieme-Aufklärungs-System (IPads)

# Senden von Daten an andere Systeme

ICM sendet alle Daten (Berichte/Kurven) als PDF nach ORBIS 

