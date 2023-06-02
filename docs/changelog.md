---
layout: default
title: "CHANGELOG"
nav_order: 4
description: "Change Log"
has_children: false
has_toc: true
---

<h1>Change Log</h1>
All notable changes to this project will be documented in this file.

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>


___
## UPDATES INCLUDED IN V1.0.12

{: .update }
Remove any reliance on JavaScript code. This is to allow organizations that have user Policies that block usage of JavaqScript in Notes applications

{: .update }
The DLAU is now backwards compatible to Lotus Notes V7.0.2

{: .update }
Modify the "Required Fields" for the "Printable Report" to make user information optional (GDPR Compliance)

{: .fix }
Adjust the layout of the "Printable Report" so that it shows the correct User Counts dependant on how the DLAU was run (with and without CCB/CCX counts)

{: .fix }
Modify the method for generating the final User Counts to occur at the end of the scanning process so that the User Counts are based on the final results, not partial results.


___
## UPDATES INCLUDED IN V1.0.11

{: .update }
Remove "# Members" column from "Deny Access Groups" View to lessen the confusiojn between the # of user names listed in the Deny Access Group versus how many Deny Access Users were discovered in the Domino environment

{: .update }
Add a disclaimer to the "Priintable Report" screen for US Federal Government clients indicating who to limit sharing the results of the DLAU with

{: .update }
Add a message to the "Scan Results" screen when 1 or more Security Observations are discovered

{: .update }
Update the "Printable Report" screen to include the "CCX License Count"

{: .update }
Modify method for displaying the number of Deny Access Groups that are captured in the DLAU

{: .fix }
The labels for CCB Users, CCX Active Users, and CCX Inactive Users were being displayed when those calculations are not being performed

{: .fix }
When calculating "Mail Users" the DLAU was not checking if the Domino Mail server that the user was configured for is an Active Domiuno server

{: .fix }
The DLAu was reporting that a LDAP Directory was in use when the configured LDAP Directory was disabled

{: .fix }
for Pre-V12 Domino environments, the "User Report Tool" area on the "Scan Results" screen was displayed with blank values when the "user Report Tool" was not selected

{: .fix }
users were receiving a sporadic "Object Variable Not Set" error when attempting to set a value onto the Scan Results controlling document

{: .fix }
If a Domino server document had a carriage return in the "Server Name" field, the DLAU would display an empty Domino server name in the "Observations" list

___
## UPDATES INCLUDED IN V1.0.10

NEW - The DLAU can now differentiate between Complete Collaboration for Business (CCB) and Complete Collaboration for External Users (CCX). New values are now displayed on the "Scan Results" page with a breakdown of each license type.

{: .update }
the "Previous Results" page has been updated to reflect the new CCB & CCX calculations

{: .fix }
A sporadic hang and eventual shut down of the HCL Notes client was occurring during the question dialog about External Users. The display of the dialog has been moved to later in the logic to stop the Notes Client issues

{: .fix }
An incorrect message was being displayed on the Printable Report page which indicated that an LDAP directory was in use when no LDAP Directories are configured

{: .fix }
The "User Information Export" was not working when a subset of the User data was selected for export

{: .fix }
On the "Observations" details page, there were labels showing for a programmatic tabbed table in the UI when they should be non-visible

{: .fix }
When viewing the Printable Report, when the user is asked for their "Client Information" the functionality would allow the user to progress without entering their information. This has changed to enforce the entry of the information prior to seeing the printable report

{: .fix }
There was a sporadic failure in completing the Scan Wizard in very specific situations if the User Report Tool Output was not indicated for older Domino environments

___
## UPDATES INCLUDED IN V1.0.9

{: .fix }
If the HCL Domino servers each have different Directory Assistance Catalogs and/or there are multiple Directory Assistance Configurations which point to the same Domino Directory, but are on separate Domino servers, the DLAU was scanning those Domino Directories miultiple times. A correction to the scan has beendesinged to ensure that only one instance of a Domino Directory is added to the scanning list

{: .update }
Numerous minor UI/UX changes, including better UI spacing to fit smaller resolution screens and a new application icon which uses the resources available in teh "HCL Domino Design Guide"

{: .update }
The version numbering system that is now being used adheres to the Versioning infomration found on the main page of this site

---
## UPDATES INCLUDED IN V1.0.0h

{: .fix }
In HCL Notes Client (64Bit version only) the NotesTimer event would crash the HCL Notes Client if it was triggered while a Dialogbox was being displayed on the user's screen

{: .new }
This version now indicates the number of Domino Mail Users that are configured in the Domino directories if they are also an Authorized User

{: .new }
If there are LDAP Directories configured in the Directory Assistance Catalog, a new Observation is captured, and an On-Screen message is displayed to the user stating that the utility currently does not support scanning of LDAP Directories

{: .update }
The original Base64 Script Library has been removed. This is in preparation for the utility to be placed into an Open-Source Repository and to follow our rules for the Apache 2.0 License

{: .update }
When scanning the HTTP and LDAP Port Settings on the Domino server documents, we now also check to see if the HTTP / LDAP port is enabled. If it is not enabled, then we ignore the additional check to see if those ports have the option "Enforce server access settings" enabled

___
## UPDATES INCLUDED IN V1.0.0g

{: .fix }
An issue was introduced in the new Re-signing functionality that would present an error after the design was resigned.

___
## UPDATES INCLUDED IN V1.0.0f

{: .fix }
A regression issue was introduced that ignored an open environment if an HCL Domino server did not have secured HTTP and / or LDAP ports

{: .new }
On the initial page that is presented with instructions for re-signing the design, there is now functionality to re-sign the design even if the user does not have access to a Domino Designer or Domino Administrator client

{: .important-title }
UI/UX - some of the wording for the Information Popup Messages to better clarify what each set of information is presenting to the user
 
___
## UPDATES INCLUDED IN V1.0.0e

{: .fix }
if an organization utilizes the "Alternative Name" field on the Person documents, those Person documents would be captured in DLAU multiple times.

{: .important-title }
UI/UX - the categorization of the "User Information" view has been changed to better display users who have access to all Domino servers and users who can only see a subset of the Domino servers

___
##UPDATES INCLUDED IN V1.0.0d

{: .fix }
If an organization has a large number of Groups in their Domino Directory (more than 65,536 Groups), the Deny Access Scan would fail. the logic for listing all Group Names has been adjusted to now accommodate up to 1,000,000 Groups in a single Domino Directory

___
## UPDATES INCLUDED IN V1.0.0c

{: .fix }
changed how the License Tracking System is identified as "running" - previously it looked for License Tracking results per available server. Now, the scan will look at the settings in the Domino Directory to see if License Tracking is enabled for each available server. this was changed for environments that have License Tracking enabled for a Domino server but there are no results for the Domino server available

{: .fix }
In some environments that have a large number of Observations, the Log document within DLAU that lists all Observations was encountering a data limit (32kb) of values. This has been corrected to allow much more data to be stored on the Log document

{: .fix }
If the client's Domino servers had a mix of different Deny Access names listed on the Security tab of the Server documents (e.g., Sever A has 2 Groups listed, Server B has 1 Group listed, Server C has 3 Groups listed) the Deny Access User calculation was not occurring correctly.

{: .fix }
The list of Domino Servers that are using a specific Deny Access Group was not fully listed on the Deny Access Group document within the utility.

{: .new }
the User Information documents now capture if the User is a Notes Mail user. This data is not displayed at this time, but will be used in a near future release that will assist in calculating Notes Mail versus Notes Application users for proper Domino Server licensing purposes (e.g., Utility Server versus Mail Server versus Enterprise Server)

{: .new }
If there is a User that is identified as having access to some, but not all, Domino servers, they are now identified as an "Authorized User - Partial Deny Access". They will now be in a different category in the "User Information" View and still count towards the "Authorized User" count.

{: .new }
On the User Information documents, when the document is opened there is now a new area titled "Server Accessibility" that lists all available Domino servers, the Domino servers that the user can access, and the Domino servers that they CANNOT access based on the Deny Access Group scans that are performed.
