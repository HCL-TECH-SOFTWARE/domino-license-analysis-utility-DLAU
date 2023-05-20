<h1><img src="/docs/assets/png/HCL+Domino_Color_Icon_300.png" alt="HCL Domino" width="75px;">HCL Domino License Analysis Utility</h1>

<h1>Understanding The Results</h1>

___
Once you have completed the scans, you will be presented with a Results page that will look similar to the image below:

![Scan Results](/docs/assets/png/14.%20Scan%20Results.png)

This is the findings from the scans that were performed. But what do these mean? Below is a description of what each area means and how the DLAU came to those values.

____
### Authorized Users
The "Authorized Users" value is the total number of users who are authorized, or have the ability, to access your HCL Domino servers. The number that is displayed is determined by many factors:

1. The number of Person documents contained in all Domino Directories in your environment
2. These Person documents have a Valid Notes Certificate
  - If there is no Notes Certificate on the Person document, there will still be an Internet Password available
3. The user's name is not listed in any of the Deny Access Groups that are in use on the HCL Domino servers
4. If the user IS listed in a Deny Access Group, the user may still be counted as an Authorized User IF the HTTP and/or LDAP ports are enabled but NOT using the same security that is in use for the remainder of the HCL Domino servers. For more information on this topic, please see the [Observations Explained](observations.md) page.

The Authorized Users number is what is used for license purposes.

___
### Person Documents
The "Person Documents" value is the total number of Person documents contained within all Domino Directories within the HCL Domino environment.

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

{: .highlight } For "Security" Observations, it is recommended to address each of them and then run the scan again. This will provide a better representation of the true Authorized Users.

For more information on each possible Observation, please open this link [Observations Explained](observations.md)