<h1><img src="https://www.hcltechsw.com/wps/wcm/connect/30a9835c-7d44-4b53-8302-9357b6e41b65/HCL+Domino_Color_Icon_300.png?MOD=AJPERES&CACHEID=ROOTWORKSPACE-30a9835c-7d44-4b53-8302-9357b6e41b65-o8PYNwY" alt="HCL Domino" width="75px;">HCL Domino License Analysis Utility</h1>

# &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;How CCB and CCX Licenses Are Calculated

HCL has two license types for HCL Domino environments:

### Complete Collaboration for Business (CCB)

Complete Collaboration for Business (CCB) licenses allow the users access to all functionality in the HCL Domino environments. these licenses are granted to employees at the organization and allows them unfettered access to all functionality that is deployed onto the HCL Domino servers. This includes the ability to modify documents within the HCL Domino applicationsthat are in use.

### Complete Collaboration for External Users (CCX)

Complete Collaboration for External Users (CCX) licenses are intended for external users of an organization. An example of an "External User" would be contract workers, Business Partners, or clients. 

This level of licensing has some restrictions that must be in place in order to identify them correctly. The most importent restriction is that the CCX users cannot have an Access Control List level higher than "Author" access. This means that a CCX user can create data (on documents) within a HCL Domino application, but cannot modify those or other documents or data.

## CCB and CCX License Calculations by the DLAU
There are two important aspects to determining CCX Licenses in the DLAU:

 

### 1. The client needs to indicate that they have external users that need to be licensed as CCX.

During the initial Domino Environment Scan if multiple Domino directories and / or multiple ORG / ORGUnit values are discovered to be in use in their Domino environment it is presumed that they may have External users. This is the method that Product Engineering and our Licensing Office have determined is the most common scenario for our clients to use.


When this scenario is discovered by the DLAU, the user will first be asked if they indeed have External Users. If they say "Yes" when prompted, they will then be presented with a dialog where they can select which additional domino Directory contains their External Users and / or they can select the ORGs / ORGUnits that indicate that the Person document is for an external user.


When the User Information scan occurs, if the Person document is either in the External Domino Directory OR their User Name contains one of the selected ORGs/ORGUnits, the aggregated data for the User Info is tagged to indicate that it is a potential CCX license (more about the "potential" in the next part).


### 2. The client must either be running Domino V12+ with Entitlement Tracking running OR provide the output from the User Report Tool. 

If no Entitlement Tracking systems can be located or if they are running V11 or lower, they will have an opportunity to select the User Report Tool output db. If neither of these systems are available, ALL users will be tagged as a CCB license.
<br/><br/><br/>
Once all of the above aligns, when the DLAu is performing the final scan, we cross reference those "potential" CCX users with the users highest ACL level based on the information obtained from the Entitlement Tracking / User Report Tool output. If the user has a maximum of "Author" or below ACL Access, they are tagged as a CCX License. If their ACL level is "Editor" or above, they are tagged as a CCB license REGARDLESS of if they are also tagged as a potential CCX license.

We also take into account when the user last accessed the Domino server(s) by also aggregating information from the "Domino User License Tracking" system. If a CCX user has accessed the Domino server(s) in the past 30 days, they are tagged as an Active CCX user. If they have not accessed the Domino server(s) in more than 30 days, they are tagged as an Inactive CCX User.

 