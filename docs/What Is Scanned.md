---
layout: default
title: "What is scanned"
nav_order: 1
description: "What is being scanned?"
has_children: true
---

<img src="/docs/assets/png/HCL+Domino_Color_Icon_300.png" alt="HCL Domino" width="75px;">

# What is scanned ?

<details close markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

Below is a description of what is scanned by the HCL Domino License Analysis Utility

___
## Scan #1: HCL Domino Server Environment

The first scan that occurs goes through the HCL Domino server environment. This scan collects all the information about the HCL Domino servers, including the following:

- Discovery of Domino Administration server
- Domino server names
- Domino Server availability (Online or Offline)
- Directory Assistance Usage
  - If DA is in use, discover all additional Domino Directories
- Check for secured HTTP and LDAP protocols
- Capture the name(s) of the Deny Access Groups that are in use on the Domino servers
- Determine if Domino V12 is in use and, if it is, list which Domino servers are using the Entitlement Tracking system
- Determine if Domino License Tracking system is running and on which Domino servers

___
## Scan #2: HCL Domino Users

The second scan that occurs goes through all Domino Directories and aggregates information from the Person documents it finds.

the information that is aggregates is as follows:

- User's name
- User's Email address
- Notes Certificate Expiry Date (if available)
- Indication if the Internet Password is set (not the actual Internet Password)
- Domino directory where the Person document resides
- Date when user last accessed a Domino Server (only if License Tracking is enabled)
- Protocols that the user's used to access the Domino servers (only if License Tracking is enabled)

Additional information is aggregated about each user during the subsequent scans.

___
## Scan #3: Deny Access Groups and User Membership

The third scan that occurs looks at the values stored on the Server document aggregated data to determine what Deny Access Groups are in use to secure the Domino servers. 

Using the list of Deny Access Groups that are in use, the scan will retrieve the Deny Access Groups, all members of those Groups and also determine if there are Group names within the Deny Access Groups. If additional Group names are discovered, the scan will also retrieve the information for those additional Groups. This recursive scanning of Groups will continue until all Group names have been processed.

Once all this information is retrieved, each of the users that were discovered during the second scan are crossed referenced against the Members of the Deny Access Groups that were discovered. This cross reference determines if the user is listed in a Deny Access Group. If a user's name is discovered, the User information will be updated to indicate this.

___
## Scan #4: Entitlement Tracking / User Report Tool Results

The third scan that occurs looks at one of two different systems:

1. Entitlement Tracking: this is a new system that was introduced in HCL Domino V12. If the client is using HCL Domino V12, this scan will always occur
2. User Report Tool Results: this is an optional system that is based on the Entitlement Tracking system that is in HCL domino V12, but has been made to be backwards compatible to Domino V9.x. Customers will need to download and run the [User Report Tool](https://support.hcltechsw.com/csm?id=kb_article&sysparm_article=KB0095328) prior to using the DLAU. 


The information that this scan retrieves will display the user's highest Access Control List level that each user has to the HCL Domino environment. This is useful in determining if the user is a CCB or a CCX license user.