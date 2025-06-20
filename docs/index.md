---
layout: default
title: "Home"
nav_order: 1
description: "HCL Domino License Analysis Utility"
has_children: true
---

[Download Latest Release](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/releases/latest){: .btn .btn-green }
[View on GitHub](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/){: .btn }

<h1> HCL Domino License Analysis Utility</h1>
This utility will assist HCL Domino Administrators in doing a health check based on deployment best practices and determining the Authorized User Count within an HCL Domino environment according to the CCB & CCX license model.

<details close markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
___
## Purpose

The purpose of this utility is to provide fast and accurate Authorized User counts for HCL Domino environments by aggregating information that a Domino Administrator would otherwise have to collect manually. It automates the process by aggregating all the information that is needed to accurately determine the Authorized User counts in a fraction of the time.

For more information, please refer this HCL Blog Post: 
[All You Ever Wanted to Know About Domino CCB Licensing and DLAU Tool](https://www.hcl-software.com/blog/domino/all-you-ever-wanted-to-know-about-domino-ccb-licensing-and-dlau-tool/)

## When to use

The HCL Domino License Analysis Utility (DLAU) should be used in environments where at least one of the HCL Domino Servers is running on a version lower than 14.5. If all of your Domino Servers are running version 14.5 (or above), you should use the integrated Domino License Dashboard which also produces a DLAU report in exactly the same format.

## Intro

{% include youtube.html id="zBPAdHMGzzo" %}


## Documentation
Learn how to use the HCL Domino License Analysis Utility with these topics:

* [Step-by-Step Instructions](instructions.md)
* [Understanding the Results](results.md)
* [How Licenses Are Calculated](licensecalc.md)
* [What is the Domino License Utility (PDF)](assets/pdf/what-Is-the-domino-license-analysis-utility.pdf)
* [What Is Scanned](scanning.md)
* [Explanation of Observations](observations.md)
* [Frequently Asked Questions](faqs.md)
* [Limitations](limitations.md)

## Compatibilty

see [system requirements](requirements.md)
## Performance & Runtime

Depending on the number of Person documents within a HCL Domino environment, the entire process can take anywhere from 45 minutes to 4 hours on average.

Person Docs | Expected runtime 
--- | --- 
1.000 | 45 minutes
5,000 | 90 minutes
10 k | 2 hours
1 Million | 15 hours

## Changes

Be sure to review the changes that are included in this release by opening the [CHANGE LOG](changelog.md)
