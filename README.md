Change Automation Account Plan
==============================

            

**![Image](https://github.com/azureautomation/change-automation-account-plan/raw/master/2016-5-26.PNG)**


**DESCRIPTION**


This runbook connects to Azure and changes Plan Type for Automation Account(s) in the Azure subscription.


You can attach a recurring schedule to this runbook to run it at a specific time. For example, you would typically want to run this runbook to switch account plan type to 'Free' when a new billing cycle
 starts, to make use of free 500 automation minutes given to a subscription for a billing cycle. And you would like to run this runbook to switch accounts’ plans type to “Basic” when free automation minutes are about to be over.


**REQUIRED ASSETS**


  *  An Automation connection asset called AzureRunAsConnection that contains the information for connecting with Azure using a service principal.  To use an asset with a different name you can pass the
 asset name as an input parameter to this runbook or change the default value for the AzureConnectionAssetName input parameter.


**REQUIRED INPUT PARAMETERS**


  *  Plan - input parameter value should be either one of 'Free' or 'Basic' string that denotes


the desired plan.


**OPTIONAL INPUT PARAMETERS**


  *  ResourceGroupName - if specified alone - used to scope the plan change only to the accounts within the specified resource group. If AccountName parameter is also provided - only this account will get the
 plan changed. 
  *  AccountName - input parameter that can be specified together with ResourceGroupName to identify a single account that needs a plan change.


NOTE: if none of optional parameters (ResourceGroupName, AcountName) is specified, the plan change
 will take an effect for all accounts under current subscription.


**OUTPUT: **List of automation accounts the change was applied too.


**OUTPUT TYPE: 
**Microsoft.Azure.Commands.Automation.Model.AutomationAccount


**AUTHOR: **Stas Kuvshinov (Microsoft)


**LASTEDIT: **2016-5-26


 


 

 

 


 


** *** *


        
    
TechNet gallery is retiring! This script was migrated from TechNet script center to GitHub by Microsoft Azure Automation product group. All the Script Center fields like Rating, RatingCount and DownloadCount have been carried over to Github as-is for the migrated scripts only. Note : The Script Center fields will not be applicable for the new repositories created in Github & hence those fields will not show up for new Github repositories.
