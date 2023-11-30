---
layout: default
title: "CHANGELOG"
nav_order: 8
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
## UPDATES INCLUDED IN V1.2.1

{: .new }
DNEXT-23861 - Added support for scanning Directory Assistance on all servers in the environment.

{: .new }
[Idea Domino-I-2499](https://domino-ideas.hcltechsw.com/ideas/DOMINO-I-2499) - DNEXT-23784 - The Customer Name, HCL Customer, etc. can now be stored in a configuration document.

{: .new }
DNEXT-24589 - Added the ability to output logging to the status bar to give the scanner an improved experience to understand progress. Set *DLAU_VERBOSE_MODE=1* in the Notes.INI before beginning the scan.

{: .new }
DNEXT-23852 - Version of DLAU is now included in the printable report as well as it is stored on the results of each scan to see how scans change over releases.

{: .new }
DNEXT-23855 - Addressing an issue when Domino is used as LDAP server

{: .update }
[Issue #54](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/issues/54) - DNEXT-24094 - Logging improvements have additional spaces around each functional area of scanning for visual improvements.

{: .fix }
[Issue #34](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/issues/34) - DNEXT-23853 - Export CCB Users does not provide content

{: .fix }
[Issue #39](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/issues/39) - DNEXT-23780 - Clicking on "Deny Access Users" opens the view "dagroups" instead of "UserInfo"

{: .fix }
[Issue #41](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/issues/41) - DNEXT-23856 - Issues with Directory Catalog not in root directory

{: .fix }
[Issue #46](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/issues/46) - DNEXT-23854 - Bug when DA is not trusted for credentials

{: .fix }
[Issue #47](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/issues/47) - DNEXT-23857 - External (CCX) Users Who are not listed in Entitlement Tracking are being recognized as CCB Users

{: .fix }
DNEXT-23771 - Clicking on the pop-up help does not work and is missing in certain situations.

{: .fix }
DNEXT-24588 - UI shifts when selecting an entry in the "Observations" field on the results page if there is a value that is too long

___
## UPDATES INCLUDED IN V1.2.0

{: .new }
DLAU is now shipped as a template

{: .new }
DLAU is now signed by Open Source Template/Domino Development

{: .update }
Modified non-warranted license included

___
## UPDATES INCLUDED IN V1.1.6

{: .fix }
Due to a failing LotusScript Method, the time difference calculation of when the user's Notes Certificate is expiring was not functioning correctly if the Notes Certificate expiry date is more than 69 years into the future.

___
## UPDATES INCLUDED IN V1.1.5

{: .update }
The methods for indicating the version of DLAU has changed. In DLAU, there is now a Shared Field that is used for displaying the DLAU version.

{: .fix }
The User Interface for the list of Observations and their decrpitions/instructions has been adjusted to provide more room for the descriptions/instructions.

{: .fix}
An adjustment has been made to the User Information scan to accommodate for Person documents that were created in a background process that do not contain all Field values that are expected.

{: .fix}
The Field Description popup has been adjusted to provide proper messages for CCB and CCX user counts.

___
## UPDATES INCLUDED IN V1.1.4

{: .new }
Each of the DLAU Scans will now log any errors that are encountered during the scan process. If a critical error is encountered, the user will be provided the opportunity to view the Scan Log.

{: .update }
For the message asking the user if they has External Users / Known Guests, the buttons on the message have been changed to "Yes" and "No" to reduce user confusion.

{: .fix }
During the User Count Calculations, there has been identified a LotusScript Regression Issue in newer versions of the Notes Client (V12.0.2) where a call to obtain a collection of documents can fail to return the proper results if more than one Search Key is used.

___
## UPDATES INCLUDED IN V1.1.3

{: .fix }
In the Scan Wizard, if the "Cancel' button is pressed prior to the completion of all scans, the user is presented with an error message "Division by zero".

{: .fix }
If there are no CCX or Known User counts, the Report page may cause a calculation error.

___
## UPDATES INCLUDED IN V1.1.2

{: .fix }
If all different User License types are not captured in a Domino environment, the Report page may cause a calculation error.

___
## UPDATES INCLUDED IN V1.1.1

{: .new }
There is now a new set of user calculations included on the "Scan Results" page to display the various User Counts for active users over a 1-year (365 days) time period.

{: .fix }
When prompted for "External User Calculations" during the HCL Domino Environment Scan, the list of Orgs/OrgUnits was not being populated properly due to an incorrect listing in the completed Domino environment scan.

{: .fix }
If a user's name in their Person document contains a quote ( " ), the Deny Access Groups scan would fail with a LotusScript error.

___
## UPDATES INCLUDED IN V1.1.0

{: .new }
On the "Printable Report" screen, add the ability for the user to send the results to HCL using a specially formatted email.

{: .new }
Calculate "Known Guests" in a similar fashion to how "CCX Users" are calculated, with the "Highest ACL Level" check to ensure that the user has ACL Level "Reader" or lower

{: .update }
Adjust "User Information" View to show the User Categories ("CCB Users", CCX Active Users", "CCX Inactive Users", "Known Guest Users")

{: .update }
Update the "Printable Report" screen to include the "CCX Inactive Count" and "Known Guests Count"

{: .update }
On the "Printable Report" screen, update the instructions for use and message for US Federal Government customers

{: .update }
Sort the Members List on the Deny Access Group documents

{: .fix }
For the "External Users" dialog, ensure that values are selected if the user clicks the "OK" button

___
## UPDATES INCLUDED IN V1.0.12

{: .update }
Remove any reliance on JavaScript code. This is to allow organizations that have user Policies that block usage of JavaScript in Notes applications

{: .update }
The DLAU is now backwards compatible to Lotus Notes V7.0.2

{: .update }
Modify the "Required Fields" for the "Printable Report" to make user information optional (GDPR Compliance)

{: .fix }
Adjust the layout of the "Printable Report" so that it shows the correct User Counts dependent on how the DLAU was run (with or without CCB/CCX counts)

{: .fix }
Modify the method for generating the final User Counts to occur at the end of the scanning process so that the User Counts are based on the final results, not partial results


___
## UPDATES INCLUDED IN V1.0.11

{: .update }
Remove "# Members" column from "Deny Access Groups" View to lessen the confusiojn between the # of user names listed in the Deny Access Group versus how many Deny Access Users were discovered in the Domino environment

{: .update }
Add a disclaimer to the "Printable Report" screen for US Federal Government clients indicating who to limit sharing the results of the DLAU with

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
The DLAU was reporting that a LDAP Directory was in use when the configured LDAP Directory was disabled

{: .fix }
For Pre-V12 Domino environments, the "User Report Tool" area on the "Scan Results" screen was displayed with blank values when the "user Report Tool" was not selected

{: .fix }
Users were receiving a sporadic "Object Variable Not Set" error when attempting to set a value onto the Scan Results controlling document

{: .fix }
If a Domino server document had a carriage return in the "Server Name" field, the DLAU would display an empty Domino server name in the "Observations" list

___
## UPDATES INCLUDED IN V1.0.10

{: .new }
The DLAU can now differentiate between Complete Collaboration for Business (CCB) and Complete Collaboration for External Users (CCX). New values are now displayed on the "Scan Results" page with a breakdown of each license type

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

{: .update }
Numerous minor UI/UX changes, including better UI spacing to fit smaller resolution screens and a new application icon which uses the resources available in teh "HCL Domino Design Guide"

{: .update }
The version numbering system that is now being used adheres to the Versioning infomration found on the main page of this site

{: .fix }
If the HCL Domino servers each have different Directory Assistance Catalogs and/or there are multiple Directory Assistance Configurations which point to the same Domino Directory, but are on separate Domino servers, the DLAU was scanning those Domino Directories miultiple times. A correction to the scan has beendesinged to ensure that only one instance of a Domino Directory is added to the scanning list

---
## UPDATES INCLUDED IN V1.0.0h

{: .new }
This version now indicates the number of Domino Mail Users that are configured in the Domino directories if they are also an Authorized User

{: .new }
If there are LDAP Directories configured in the Directory Assistance Catalog, a new Observation is captured, and an On-Screen message is displayed to the user stating that the utility currently does not support scanning of LDAP Directories

{: .update }
The original Base64 Script Library has been removed. This is in preparation for the utility to be placed into an Open-Source Repository and to follow our rules for the Apache 2.0 License

{: .update }
When scanning the HTTP and LDAP Port Settings on the Domino server documents, we now also check to see if the HTTP / LDAP port is enabled. If it is not enabled, then we ignore the additional check to see if those ports have the option "Enforce server access settings" enabled

{: .fix }
In HCL Notes Client (64Bit version only) the NotesTimer event would crash the HCL Notes Client if it was triggered while a Dialogbox was being displayed on the user's screen

___
## UPDATES INCLUDED IN V1.0.0g

{: .fix }
An issue was introduced in the new Re-signing functionality that would present an error after the design was resigned

___
## UPDATES INCLUDED IN V1.0.0f

{: .new }
On the initial page that is presented with instructions for re-signing the design, there is now functionality to re-sign the design even if the user does not have access to a Domino Designer or Domino Administrator client

{: .update }
UI/UX - some of the wording for the Information Popup Messages to better clarify what each set of information is presenting to the user

{: .fix }
A regression issue was introduced that ignored an open environment if an HCL Domino server did not have secured HTTP and / or LDAP ports

___
## UPDATES INCLUDED IN V1.0.0e

{: .update }
UI/UX - the categorization of the "User Information" view has been changed to better display users who have access to all Domino servers and users who can only see a subset of the Domino servers

{: .fix }
if an organization utilizes the "Alternative Name" field on the Person documents, those Person documents would be captured in DLAU multiple times

___
## UPDATES INCLUDED IN V1.0.0d

{: .fix }
If an organization has a large number of Groups in their Domino Directory (more than 65,536 Groups), the Deny Access Scan would fail. the logic for listing all Group Names has been adjusted to now accommodate up to 1,000,000 Groups in a single Domino Directory

___
## UPDATES INCLUDED IN V1.0.0c

{: .new }
the User Information documents now capture if the User is a Notes Mail user. This data is not displayed at this time, but will be used in a near future release that will assist in calculating Notes Mail versus Notes Application users for proper Domino Server licensing purposes (e.g., Utility Server versus Mail Server versus Enterprise Server)

{: .new }
If there is a User that is identified as having access to some, but not all, Domino servers, they are now identified as an "Authorized User - Partial Deny Access". They will now be in a different category in the "User Information" View and still count towards the "Authorized User" count

{: .new }
On the User Information documents, when the document is opened there is now a new area titled "Server Accessibility" that lists all available Domino servers, the Domino servers that the user can access, and the Domino servers that they CANNOT access based on the Deny Access Group scans that are performed

{: .fix }
changed how the License Tracking System is identified as "running" - previously it looked for License Tracking results per available server. Now, the scan will look at the settings in the Domino Directory to see if License Tracking is enabled for each available server. this was changed for environments that have License Tracking enabled for a Domino server but there are no results for the Domino server available

{: .fix }
In some environments that have a large number of Observations, the Log document within DLAU that lists all Observations was encountering a data limit (32kb) of values. This has been corrected to allow much more data to be stored on the Log document

{: .fix }
If the client's Domino servers had a mix of different Deny Access names listed on the Security tab of the Server documents (e.g., Sever A has 2 Groups listed, Server B has 1 Group listed, Server C has 3 Groups listed) the Deny Access User calculation was not occurring correctly

{: .fix }
The list of Domino Servers that are using a specific Deny Access Group was not fully listed on the Deny Access Group document within the utility