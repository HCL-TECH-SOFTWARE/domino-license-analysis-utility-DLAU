---
layout: default
title: "Understanding Results"
parent: "Home"
nav_order: 7
description: "Understanding the Results"
has_children: false
---

<h1>Understanding The Results</h1>

<details close markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

___
Once you have completed the scans, you will be presented with a Results page that will look similar to the image below:

![Scan Results](assets/images/png/14-scan-results.png)

This is the findings from the scans that were performed. But what do these mean? Below is a description of what each area means and how the DLAU came to those values.

____
### Authorized Users
The "Authorized Users" value is the total number of users who are authorized, or have the ability, to access your HCL Domino servers. The number that is displayed is determined by many factors:

1. The number of Person documents contained in all Domino Directories in your environment
2. These Person documents have a Valid Notes Certificate
  - If there is no Notes Certificate on the Person document, there will still be an Internet Password available
3. The user's name is not listed in any of the Deny Access Groups that are in use on the HCL Domino servers
4. If the user IS listed in a Deny Access Group, the user may still be counted as an Authorized User IF the HTTP and/or LDAP ports are enabled but NOT using the same security that is in use for the remainder of the HCL Domino servers. For more information on this topic, please see the [Observations](de-de/observations.md) page.

The Authorized Users number is what is used for license purposes.***

___
### CCB Users
The "CCB Users" value is the total number of Internal Employees of the organization that have the ability to use and access the Domino environment.***

As noted in the CCB License Agreement:

*Licensee must obtain separate, dedicated CCB entitlements for each Internal User. “Internal User” shall mean permanent or temporary or transient employee, or person paid for, or acting on behalf of Licensee’s Enterprise ("Licensee’s Enterprise" is Licensee and all Affiliates per
MLA §1.1) who is assigned A/U access to the Program in any manner directly or indirectly (for example: via a multiplexing program, device, or application server) through any means.
In addition, Licensee must obtain separate, dedicated CCB entitlements to assign A/U credentials to a specific task or role or other such entities.*

___
### CCX Users
The "CCX Users" value is the total number of External Users of the organization that have gthe ability to Create and Read documents in the Domino environment.***

As noted in the CCB License Agreement:

*Licensee must obtain separate, dedicated CCX entitlements for
each External User. An "External User" is a unique person not included in above Internal Users, who is assigned Authorized User access to the Program with restricted maximum level of Domino application access (ACL) as "AUTHOR". A CCX A/U entitlement is unique, but may be reassigned to another user after thirty (30) days of inactivity.*

___
### Inactive CCX Users

This number is for informational purposes only. An inactive CCX user will not count towards CCX entitlements.
Those are CCX users who technically can log in, but have not been logging in within the past 30 days of time.
Inactive CCX Users shown in the column "All 365 days" is the number of CCX users who have never logged in within the past 365 days.

___

### Person Documents
The "Person Documents" value is the total number of Person documents contained within all Domino Directories within the HCL Domino environment.***

___
### Mail Users
The "Mail Users" value is the total number of users that are configured for HCL Domino Mail access. This is also an important value when determining the type of license that is required if you are not already licensed for Complete Collaboration for Business (CCB) licenses.

___
### Deny Access Groups
The "Deny Access Groups" value is the number of Deny Access Groups that are in use on your HCL Domino servers. This number also includes any Recursive Groups that were discovered while locating the Deny Access Groups that are in use.

___
### Administration Server
This is the HCL Domino Administration server that was used for the basis of all scans that are performed.

__
### All Domino Servers in Environment
This is a list of all HCL Domino servers that are configured in the environment. This is based on the Server documents discovered in all Domino Directories that were scanned.

This list will also show if the server is online (Available) or offline.

___
### Entitlement Tracking Enabled Servers
For HCL Domino V12.x environments, a new system titled "Entitlement Tracking" was introduced. This list is all the HCL Domino servers in the environment that is running the Entitlement Tracking system.

For more information on "Entitlement Tracking System", please refer to [Entitlement Tracking System](https://help.hcltechsw.com/domino/12.0.0/admin/admn_entitlementtracking.html)

___
### User Report Tool Output Location
For HCL Domino servers V9 - V11.x, there is a system called the "User Report Tool". This is a system which is equivalent to the "Entitlement Tracking System", but it has been made to work on versions of HCL Domino that are less than V12.x

The value that is shown is where the results of the User Report Tool is located.

For more information on the "User Report Tool", please refer to: [User Report Tool Knowledgebase document](https://support.hcltechsw.com/csm?id=kb_article&sysparm_article=KB0095328)

___
### Directory Assistance Information
This value will show where the Directory Assistance Catalog is located in your HCL Domino environment.

If the Directory Assistance system is not in use, this information will not be shown.

___
### Additional Domino Directories
This value will list all additional Domino Directories that are in your organization.

If the first value listed is shown in the color Blue, this indicates that the Domino directory listed is being used to list "External Users" - users that are not employees of the organization but are still being granted limited access to the HCL domino servers.

If the Directory Assistance system is not in use, this information will not be shown.

___
### Observations
The values shown in the 'Observations" section list all Environment Observations that were discovered during the scanning process.

The Observations can range from "Informational" (minor items that can improve the value of the data collected), "Warnings" (items that may be an issue in your HCL Domino environment), and "Security" (items that will affect the secure nature of your HCL Domino environment and will have an effect on the "Authorized User" count).

{: .notice }
For "Security" Observations, it is recommended to address each of them and then run the scan again. This will provide a better representation of the true Authorized Users.

For more information on each possible Observation, please open this link [Anmerkungen](de-/deobservations.md)

*** If there were any non-Domino users found in the Entitlement Tracking part of the scan, they will be included in these counts.