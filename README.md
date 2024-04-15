# Using AzureHound
Steps for Using AzureHound


## Step 1: Obtain AzureHound
Download from https://github.com/bloodhoundad/azurehound/releases/tag/rolling


## Step 2: Login to Azure Portal using Web Browser
You're now looking for a JWT to gain access to Microsoft Graph.  
  
Login to https://portal.azure.com, search for anything (e.g. ADFS MFA) and click on the result.  
  
![image](https://github.com/benlee105/Using-AzureHound/assets/62729308/23fde5c7-e47e-4c2c-9a0c-af6e04b44684)
  
Now check your browser's Session Storage.   
  
`In FireFox > F12 > Storage tab > Session Storage > https://portal.azure.com`  
  
Look at the the "homeAccountId" Values. You want a JWT that authorizes access to **https://graph.windows.net**.  
  
Right click the "secret" section and Copy it.  

![image](https://github.com/benlee105/Using-AzureHound/assets/62729308/c82e0aef-66a1-41d3-a179-38157d595af1)


## Step 3: Getting the tenant ID
In Azure Portal, click on the gear icon and see "Domain".  

The value under Domain is your tenant ID.  
  
![image](https://github.com/benlee105/Using-AzureHound/assets/62729308/f216ff11-2a85-4c4b-aaee-2a8c0190f28a)



## Step 4: Testing AzureHound
In powershell, navigate to where you downloaded azurehound.exe  

Test the command below  
`.\azurehound.exe -j "eyJ..." -t "xxx.onmicrosoft.com" list users`  
- -j is where you input the JWT
- -t is to input tenant ID
- list users displays users in the Azure tenant

![image](https://github.com/benlee105/Using-AzureHound/assets/62729308/1c5f034e-2f0d-433c-8ec9-ee632d19ae75)


## Step 5: Executing AzureHound
`.\azurehound.exe -j "eyJ..." -t "xxx.onmicrosoft.com" list -o output.json`  
- -j is where you input the JWT
- -t is to input tenant ID
- list displays everything in the Azure tenant
- -o lets you output to json file for ingestion to BloodHound


![image](https://github.com/benlee105/Using-AzureHound/assets/62729308/b8a10c84-42d2-48e7-975b-24181831eb3f)
