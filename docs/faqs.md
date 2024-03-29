---
layout: default
title: "FAQ"
nav_order: 9
description: "Frequently Asked Questions"
parent: "Home"
has_children: false
---
<h1>Frequently Asked Questions</h1>

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>


### Do I need to change the configuration of my HCL Domino servers?

No. This utility does not require any additional functionality to be added to ANY HCL Domino servers. It runs completely on the local drive of the HCL Domino Administrator who is running the utility. For the tool to function properly your environment needs to be in line with the [System Requirements](requirements.md)

### Is this a Licensing Audit? Will I need to involve our legal / compliance team(s)?

It is important to note that DLAU is not conducting a license audit, which is always an in-depth hindsight analysis. Instead, DLAU is creating a baseline to help you and HCLSoftware have a meaningful forward-looking conversation for your renewal or restart or move to CCB or Volt MX Go. The baseline must be augmented by the customer in terms of future deployment plans as the customer is continually responsible for license compliance going forward.

### Will the process block my Notes Client?

The scans within the utility run in a background task. The user’s Notes Client can be used as normal during the scanning processes. The user only needs to “check in” periodically to see if the current scan is complete and to progress to the next scan.

### How long will the process take?

It depends, typically it should take 1 to 3+ hours, depending on the number of Person documents and HCL Domino servers in the environment. For example, a small deployment (~200 users) will take 45 minutes, medium deployments (~5000 users) will take under 2 hours.
Further reference information on how long the process may take on the [home page](index.md#performance--runtime) of this project

### How do I see scanning updates in the status bar?

Set *DLAU_VERBOSE_MODE=1* in your Notes.INI, restart the Notes client, then begin the scan. While the scan is taking place you will now see additional output in the Notes Client's status bar including a time stamp to help ensure you that progress is continuing. As of DLAU 1.2.2 the additional output will also appear in the scan log.

### How can I substantiate needed entitlements?

Within the “Scan Results” page, there is a button labeled “View Printable Result”. When that is clicked, you will be presented with a printable report that you can share with HCL as a PDF (Print to PDF) if needed for renewal discussions. The data contained in this PDF is in line with our [privacy statement](privacy.md)

### How accurate are the results of the scans?

While this is not an audit tool, it usually provides accurate information of your current environment. If you have any doubts of the report being incorrect, please reach out to your HCL representative or [report an issue](issues.md).
Statistically, our early adopters of the utility are reporting a 96% accuracy. The 4% generally are seen to be special Administration or Design Signing users.

add new FAQ about CCB / CCX calculations and then link to the June 29 Blog Post

### What is the difference between CCB and CCX Licenses?

For more information on the differences between CCB and CCX licenses, please refer this HCL Blog Post:
[All You Ever Wanted to Know About Domino CCB Licensing and DLAU Tool](https://blog.hcltechsw.com/domino/all-you-ever-wanted-to-know-about-domino-ccb-licensing-and-dlau-tool/?referrer=opensource.hcltechsw.com/domino-license-analysis-utility-DLAU/)