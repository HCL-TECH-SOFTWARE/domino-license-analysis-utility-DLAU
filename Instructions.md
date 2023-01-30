<h1><img src="https://www.hcltechsw.com/wps/wcm/connect/30a9835c-7d44-4b53-8302-9357b6e41b65/HCL+Domino_Color_Icon_300.png?MOD=AJPERES&CACHEID=ROOTWORKSPACE-30a9835c-7d44-4b53-8302-9357b6e41b65-o8PYNwY" alt="HCL Domino" width="75px;">HCL Domino License Analysis Utility</h1>

<h2 align="center">How to use the DLAU</h2>

___
## Prerequisite - Download Utility
Prior to continuing through this documentation, you will need to download the HCL Domino License Analysis Utility (DLAU) into your Notes Data directory.

DLAU is designed to work most efficiently on a local hard drive, so there is no need to copy/replicate the DLAU onto any of your HCL Domino servers.

[Click here to download the DLAU file](https://github.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/raw/main/DLAU%20download/licenseanalysis_V1.0.0h.nsf)

___
## Step 1 - Launch and Resign Design of DLAU
Once the DLAU file has been downloaded and transfered into your Notes Data directory, it is now time for you to open the utility and re-sing the design.

Re-signing the design is required in order for the environment scans to run in the background. Running the scans in the background will allow you to continue using your HCL Notes Client while the processing is taking place.

The simplest method for opening the utility is to double-click on it in the File Explorer application.

Once the utility is open, you should see the screen below which contains instructions on how to re-sign the design of the utility:

<a href="..//main/images/1.%20Initial%20Launch%20-%20Resign.png"><img src="..//main/images/1.%20Initial%20Launch%20-%20Resign.png" width="400px"></a>

Depending on your experience level and how much you want to moniutor the re-singing process, select the appropriate method listed.

___
## Step 2 - Re-Launch the DLAU
Now that the design of the DLAU has been re-singed, you will need to re-open the utility. When you initially opened the DLAU a Domino applicaiton icon will have been added to your Workspace. Locate and open the DLAU.

Once opened, you will be presented with the following screen:

<a href="..//main/images/2.%20Wizard%20Initial%20Launch.png"><img src="..//main/images/2.%20Wizard%20Initial%20Launch.png" width="400px"></a>

Once opened, you will be provided some high level information about what the utility will be performing. It also provides you with information on other systems that can contribute to a cleaner result from the DLAU. If you would like to run and/or install the additional systems, click on the links under the "Important Links" area.

To begin the scanning processes, click on the "Next" button.

____
## Step 3 - HCL Domino Environment Scan
The first scan is the "HCL Domino Environment Scan". This scan concentrates on the HCL Domino servers, their availability, usage of Deny Access Groups, and whether they are properly secured.

A listing of what is scanned during this step is below:

* Discovery of Domino Administration server
* Domino server names
* Domino Server availability (Online or Offline)
* Directory Assistance Usage
   * If DA is in use, discover all additional Domino Directories
* Check for secured HTTP and LDAP protocols
* Capture the name(s) of the Deny Access Groups that are in use on the Domino servers
* Determine if Domino V12 is in use and, if it is, list which Domino servers are using the Entitlement Tracking system
* Determine if Domino License Tracking system is running and on which Domino servers


To begin the HCL Domino Environment Scan, click the **Start Environment Scan Now** button:

<a href="..//main/images/3.%20Environment%20Scan%20-%20Start.png"><img src="..//main/images/3.%20Environment%20Scan%20-%20Start.png" width="400px"></a>

The HCL Domino Environment scan will take approximately 5 minutes to complete, depending on the number of HCL Domino Servers in your environment.

If your organization is using additional Domino Directories via the Directory Assistance Catalog, you will be asked if any of those additional Domino directories are being used to register **External Users**. An **External User** is a user that is not a direct employee of your organization and has a maximum Access Control List level of "Author" to the Domino applications on your HCL Domino servers. This is better known as a **Complete Collaboration for External Users** (CCX) license.

If this is the scenario in your environment, you will be presented the following message:

<a href="..//main/images/4.%20Environment%20Scan%20-%20External%20Directory%20Questions.png"><img src="..//main/images/4.%20Environment%20Scan%20-%20External%20Directory%20Questions.png" width="400px"></a> 

If you select "yes" as your answer, you will be presented with the following dialog which will provide you the opportunity to select either the Additional Domino Directory for CCX users and/or the ability to select the OrgUnit / Org that identifies the CCX users:

<a href="..//main/images/5.%20Environment%20Scan%20-%20External%20Selections.png"><img src="..//main/images/5.%20Environment%20Scan%20-%20External%20Selections.png" width="400px"></a> 
