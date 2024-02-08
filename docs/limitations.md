---
layout: default
title: "Known Limitations"
nav_order: 5
description: "Known Limitations"
has_children: false
---

<h1>Known Limitations</h1>

Below is a list of current limitations that will be encountered in certain HCL Domino environments when using the Domino License Analysis Utility

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

___
## LDAP/ActiveDirectory 

Coming soon
{: .label .label-yellow }

If one or more of your Domino servers are configured to use an external LDAP/Active Directory for authentication of web users, these types of directory connections are not currently being scanned.

Therefore, a manual counting of all users who are accessing the HCL domino server(s) in this manner will need to take place. 

{: .highlight } 
We are working on scanning LDAP / AD directories and cross reference the users found in those against the findings in the License Tracking System.

___
## Multiple/disconnected HCL Domino Domains

For HCL Domino environments that have different, unique Domino Domains that are not connected using any type of Directory Assistance, the DLAU will only scan the Domino Domain that was discovered based on your current HCL Notes Location document.

In order to scan all domino Domains in this scenario, you will need to create / use different Location documents, one per Domino domain, that list the Domino Administration server as the "Home/Mail Server".

It is required that you use different copies of the DLAU, one copy per Domino Domain. By using multiple copies of DLAU, you will retain the informaiton for each Domino Domain that has been scanned.

Then, a manual deduplication of discovered Notes Users will need to occur. This is to ensure that a single user that is listed in each Domino Domain is only counted once.

{: .note }
We are working on a solution that will allow for multiple Domino Domains to be scanned at the same time by allowing multiple Domino Administration servers to be selected.

___
## Directory Assistance on Servers other than Administration Server

As of DLAU 1.2.1 this limitation has been removed.

{: .highlight } 
Note: this limitation was removed as part of the work done in DNEXT-23861 to enhance Directory Assistance scanning.
