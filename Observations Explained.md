<h1><img src="https://www.hcltechsw.com/wps/wcm/connect/30a9835c-7d44-4b53-8302-9357b6e41b65/HCL+Domino_Color_Icon_300.png?MOD=AJPERES&CACHEID=ROOTWORKSPACE-30a9835c-7d44-4b53-8302-9357b6e41b65-o8PYNwY" alt="HCL Domino" width="75px;">HCL Domino License Analysis Utility</h1>

During the scanning processes, a number of HCL Domino environment observations are captured. These can range form simple informational observations to more serious security vulnerabilities in a clients HCL Domino environment.

These observations are captured while the scans are occurring and are provided to the user once all scans are completed.

Instructions on how to remediate any HCL Domino environment settings to correct the observations are provided within the DLAU interface.

Below is a list of the Observations that are captured with a description of what the observation means.

**Special Note:** information in **_Bold Italicized_** letters are for example purposes only. these values will vary between clients.

___
## Security Observations

The HCL Domino Server **_"Production/ACME"_** is not properly secured for HTTP traffic
- This observation indicates that HTTP traffic is not using the same level of access security to your HCL Domino servers. When this is the case, even if a user's name is listed in a Deny Access Group, the user has the ability to access the HCL domino servers using a web browser. The HTTP port needs to be properly secured in order to report on user's who are listed in a Deny Access Group properly, else they will be counted as an Authorized User


The HCL Domino Server **_"Production/ACME"_** is not properly secured for LDAP traffic
- This observation indicates that the LDAP traffic is not using the same level of access security to your HCL Domino servers. When this is the case, even if a user's name is listed in a Deny Access Group, the user has the ability to access the HCL domino servers using a web browser. The LDAP port needs to be properly secured in order to report on user's who are listed in a Deny Access Group properly, else they will be counted as an Authorized User

The HCL Domino Server **_"Production/ACME"_** is not using any Deny Access Groups to secure server access
- This observation is reporting that a Deny Access Group is not listed on the specified HCL Domino server document. therefore, anyone with credentials, either using a Notes ID or internet credentials, has the ability to access the HCL Domino server. Even if an employee leaves the client's organization, they would still have the ability to access the HCL Domino environment.

The Deny Access Group named _*"ACME Deny Access"_** appears to be missing from your Domino Directory
- This observation is reporting that, even though there is a Deny Access group listed on the Domino server document, the actual Deny Access group does not exist. In this scenario, the usage of the Deny Access group will be ignored, and in turn anyone with credentials to the HCL Domino environment will have access to the HCL Domino server.

___
## Warning Observations

The HCL Domino Server **_"International/ACME"_** appears to be Offline
- This observation is indicating that the server listed is not accessible during the HCL Domino Environment scan. This can indicate either a connectivity issue or that the HCL Domino server is, in fact, offline. If the HCL Domino server is offline purposefully, there is nothing more for the user to do. But if the listed HCL Domino server is supposed to be accessible, this observation is highlighting a potential connectivity issue for all users.

The HCL Domino Directory configured in Directory Assistance cannot be located - Server: **_Production/ACME_** (file name: **_external_names.nsf_**)
- This observation is indicating that the listed additional Domino Directory that is configured in the Directory Assistance Catalog is not accessible and/or available. This observation can be causing connectivity or other issues for the users that are listed in the additional Domino Directory

The Directory Assistance configuration **_"DomainName" (DomainTitle)_** Is a LDAP Directory
- This observation indicates that the HCL Domino environment has a Directory Assistance configuration that connects to a LDAP Directory. Scanning of LDAP Directories is not yet supported by this utility. Therefore, the total Authorized Users that are being reported may not be representative of the total number of possible Authorized Users in your environment.

___
## Informational Observations

The License Tracking task is not running on the HCL Domino server **_Production/ACME_**
- This observation is reporting that the HCL Domino server listed does not have the Domino License Tracking system running. As this is an optional system , there is no immediate need for the Domino Administrator to make any changes. However, having the Domino License Tracking system running will provide better results for the Domino Administrator when they review the aggregated User Information

The Deny Access Group named **_"ACME More Deny Access"_** has no Members listed
- This observation is indicating that the Deny Access group that is in use within the HCL Domino environment has no user names within its Members list. This is indicated as an Informational Observation as there may be other Group names listed in the Members list.
