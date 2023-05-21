---
layout: default
title: "FAQ"
nav_order: 6
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

This utility does not require any additional functionality to be added to ANY HCL Domino servers. It runs completely on the local drive of the HCL Domino Administrator who is running the utility
 

### Is this a Licensing Audit? Will I need to involve our legal / compliance team(s)?

This utility is not an audit tool. It is meant to automate the manual processes that the HCL Domino Administrator would need to perform in order to obtain the same results. This utility will perform the same analysis that the HCL Domino Administrator would have to perform, but with 100% accuracy.

 
### Will this type of analysis block my Notes Client?

The scans within the utility run in a background task. The user’s Notes Client can be used as normal during the scanning processes. The user only needs to “check in” periodically to see if the current scan is complete and to progress to the next scan.


### How long will the process take?

It depends, typically it should take 1 to 3+ hours, depending on the number of Person documents and HCL Domino servers in the environment. For example, a small deployment (~200 users) will take 45 minutes, medium deployments (~5000 users) will take under 2 hours. 


### How can I substantiate needed entitlements?

Within the “Scan Results” page, there is a button labeled “View Printable Result”. When that is clicked, you will be presented with a printable report that you can share with HCL as a PDF (Print to PDF) if needed for renewal discussions.

 
### How accurate are the results of the scans?

Our early adopters of the utility are reporting a 96% accuracy. The 4% generally are seen to be special Administration or Design Signing users.
