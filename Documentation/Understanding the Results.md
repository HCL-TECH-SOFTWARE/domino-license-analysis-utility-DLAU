<h1><img src="https://www.hcltechsw.com/wps/wcm/connect/30a9835c-7d44-4b53-8302-9357b6e41b65/HCL+Domino_Color_Icon_300.png?MOD=AJPERES&CACHEID=ROOTWORKSPACE-30a9835c-7d44-4b53-8302-9357b6e41b65-o8PYNwY" alt="HCL Domino" width="75px;">HCL Domino License Analysis Utility</h1>

<h1>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Understanding The Results</h1>

___
Once you have completed the scans, you will be presented with a Results page that will look similar to the image below:

<a href="https://raw.githubusercontent.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/main/images/14.%20Scan%20Results.png"><img src="https://raw.githubusercontent.com/HCL-TECH-SOFTWARE/domino-license-analysis-utility-DLAU/main/images/14.%20Scan%20Results.png" width="500px"></a>

This is the findings from the scans that were performed. But what do these mean? Below is a description of what each area means and how the DLAU came to those values.

____
### Authorized Users
The "Authorized Users" is the total number of users who are authorized, or have the ability, to access your HCL Domino servers. The number that is displayed is determined by many factors:

1. The number of Person documents contained in all Domino Directories in your environment
2. These Person documents have a Valid Notes Certificate
  - If there is no Notes Certificate on the Person document, there will still be an Internet Password available
3. The user's name is not listed in any of the Deny Access Groups that are in use on the HCL Domino servers
4. If the user IS listed in a Deny Access Group, the user may still be counted as an Authorized User IF the HTTP and/or LDAP ports are enabled but NOT using the same security that is in use for the remainder of the HCL Domino servers. For more information on this topic, please see the [Observations Explained](Observations%20Explained.md) page.