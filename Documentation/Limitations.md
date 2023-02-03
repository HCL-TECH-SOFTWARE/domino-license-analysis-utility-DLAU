<h1><img src="https://www.hcltechsw.com/wps/wcm/connect/30a9835c-7d44-4b53-8302-9357b6e41b65/HCL+Domino_Color_Icon_300.png?MOD=AJPERES&CACHEID=ROOTWORKSPACE-30a9835c-7d44-4b53-8302-9357b6e41b65-o8PYNwY" alt="HCL Domino" width="75px;">HCL Domino License Analysis Utility</h1>

#&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Limitations In The DLAU

Below is a list of current Limitations that will be encountered in certainHCL Domino environments when using the DLAU

___
## LDAP/AD Scanning

If you organization uses a LDAP Directory or Active Directory for users credentials to login to HCL Domino web applications, these types of directory connections are not currently being scanned.

Therefore, a manual counting of all users who are accessing the HCL domino server(s) in this manner will need to take place.

If you are using the License Tracking System on your HCL Domino serves, you can use the data contained within the "Domino User License Tracking" Notes application to determine how many users from external Directories are accessing your HCL Domino servers.

#### Special Note:
We are working on a solution to also scan configured LDAP / AD directories and cross reference the users found in those against the findings in the License Tracking System.

___
## HCL Domino Environments with Multiple, disconnected Domains

For HCL Domino environments that have different, unique Domino Domains that are not connected using any type of Directory Assistance, the DLAU will only scan the Domino Domain that was discovered based on your current HCL Notes Location document.

In order to scan all domino Domains in this scenario, you will need to create / use different Location documents, one per Domino domain, that list the Domino Administration server as the "Home/Mail Server".

It is required that you use different copies of the DLAU, one copy per Domino Domain. By using multiple copies of DLAU, you will retain the informaiton for each Domino Domain that has been scanned.

Then, a manual deduplication of discovered Notes Users will need to occur. This is to ensure that a single user that is listed in each Domino Domain is only counted once.

#### Special Note: 
We are working on a solution that will allow for multiple Domino Domains to be scanned at the same time by allowing multiple Domino Administration servers to be selected.

___
## Directory Assistance In Use on HCL Domino Servers Other Than Administration Server

The DLAU will only process additional Domino Directories if the Domino Administration server is using the Directory Assistance system.

If you have the scenario where your Domino Administration server does NOT use Directory Assistance, but one or more of your other Domino servers ARE using Directory Assistance, the additional Domino directories will not be processed.

#### Special Note: this issue is being assesed now and plans for advanced Directory Assistance scanning will be scheduled for a near future release.