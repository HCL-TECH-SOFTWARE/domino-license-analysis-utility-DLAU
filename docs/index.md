---
layout: default
title: "Overview"
nav_order: 1
description: "HCL Domino License Analysis Utility"
has_children: true
---

[Download Latest Release](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/releases/latest){: .btn }
[View it on GitHub](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/){: .btn }

---

# HCL Domino License Analysis Utility

<details close markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>


This utility will assist HCL Domino Administrators in determining your Authorized User Count within their HCL Domino environment according to the CCB & CCX license model.

## Purpose
The purpose of this utility is to provide fast and accurate Authorized User counts for HCL Domino environments by aggregating information that a Domino Administrator would otherwise have to collect manually.

In large deployments **without the use of this utility** this process can be very time consuming, taking days, if not weeks, to determine who can access the HCL Domino environment.

HCL Domino Administrators will no longer need to scour though all the different systems to determine who their Authorized Users are!

The DLAU automates the process by aggregating all the information that is needed to accurately determine the Authorized User counts in a fraction of the time.

## Download
If you have already used and/or understand how this new utility works, you can proceed directly to the file download.

***[Click Here](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/releases/latest) to download the latest release***

Be sure to review the changes that are included in this release by opening the [CHANGE LOG](changelog.md)

## Documentation

Learn how to use the HCL Domino License Analysis Utility with these topics:

* [Step-by-Step Instructions](/docs/instructions.md)
* [Understanding the Results](/docs/results.md)
* [How Licenses Are Calculated](/docs/licensecalc.md)
* [PDF Presentation of the HCL Domino License Utility](/docs/assets/pdf/HCL%20Domino%20License%20Analysis%20Utility%20-%20What%20Is%20It.pdf)
* [What Is Scanned](/docs/scanning.md)
* [Explanation of Observations](/docs/observations.md)
* [Frequently Asked Questions](/docs/faqs.md)
* [Limitations](/docs/limitations.md)
___
## Runtime

Depending on the number of Person documents within a HCL Domino environment, the entire process can take anywhere from 45 minutes to 4 hours on average.

 Person Docs | Expected runtime 
--- | --- 
1.000 | 45 minutes
5,000 | 90 minutes
10 k | 2 hours
1 Million | 15 hours
