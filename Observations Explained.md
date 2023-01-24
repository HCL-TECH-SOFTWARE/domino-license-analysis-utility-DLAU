<h1><img src="https://www.hcltechsw.com/wps/wcm/connect/30a9835c-7d44-4b53-8302-9357b6e41b65/HCL+Domino_Color_Icon_300.png?MOD=AJPERES&CACHEID=ROOTWORKSPACE-30a9835c-7d44-4b53-8302-9357b6e41b65-o8PYNwY" alt="HCL Domino" width="75px;">HCL Domino License Analysis Utility</h1>

During the scanning processes, a number of HCL Domino environment observations are captured. These can range form simple informational observations to more serious security vulnerabilities in a clients HCL Domino environment.

These observations are captured while the scans are occurring and are provided to the user once all scans are completed.

Instructions on how to remediate any HCL Domino environment settings to correct the observations are provided within the DLAU interface.

Below is a list of the Observations that are captured with a description of what the observation means.

**Special Note:** information in ** *Bold Italicized* ** letters are for example purposes only. these values will vary between clients.

___
## Security Observations

The HCL Domino Server ** *"Production/ACME"* ** is not properly secured for HTTP traffic
- This observation indicates that HTTP traffic is not using the same level of access security to your HCL Domino servers. When this is the case, even if a user's name is listed in a Deny Access Group, the user has the ability to access the HCL domino servers using a web browser. The HTTP port needs to be properly secured in order to report on user's who are listed in a Deny Access Group properly, else they will be counted as an Authorized User


The HCL Domino Server ** *"Production/ACME"* ** is not properly secured for LDAP traffic
- This observation indicates that the LDAP traffic is not using the same level of access security to your HCL Domino servers. When this is the case, even if a user's name is listed in a Deny Access Group, the user has the ability to access the HCL domino servers using a web browser. The LDAP port needs to be properly secured in order to report on user's who are listed in a Deny Access Group properly, else they will be counted as an Authorized User

The HCL Domino Server ** *"Production/ACME"* ** is not using any Deny Access Groups to secure server access
- This observation is reporting that a Deny Access Group is not listed on the specified HCL Domino server document. therefore, anyone with credentials, either using a Notes ID or internet credentials, has the ability to access the HCL Domino server. Even if an employee leaves the client's organization, they would still have the ability to access the HCL Domino environment.

The Deny Access Group named ** *"ACME Deny Access"* ** appears to be missing from your Domino Directory
- This observation is reporting that, even though there is a Deny Access group listed on the Domino server document, the actual Deny Access group does not exist. In this scenario, the usage of the Deny Access group will be ignored, and in turn anyone with credentials to the HCL Domino environment will have access to the HCL Domino server.