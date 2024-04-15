# Using AzureHound
Steps for Using AzureHound


## Step 1: Obtain AzureHound
https://github.com/bloodhoundad/azurehound/releases/tag/rolling


## Step 2: Login to Azure Portal using Web Browser
You're now looking for a JWT to gain access to Microsoft Graph.  
  
Login to https://portal.azure.com, search for anything (e.g. ADFS) and click on any result.  
  
Now check your browser's Session Storage.   
  
`In FireFox > F12 > Storage tab > Session Storage > https://portal.azure.com`  
  
## Step 3: Getting the JWT 
Look at the the "homeAccountId" Values. You want a JWT that authorizes access to **https://graph.windows.net** .

Right click the "secret" section and Copy it  

![image](https://github.com/benlee105/Using-AzureHound/assets/62729308/c82e0aef-66a1-41d3-a179-38157d595af1)


## Step 4: Executing AzureHound


