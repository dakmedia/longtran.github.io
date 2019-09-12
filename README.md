### How to create a UPN Suffix on Active Directory
- GUI
- Powershell

#### GUI
Step 1:  **Server Manager**, selete menu **Tools**, choose **Active Directory Domains and Trusts**
![](images/image1.jpg)
Step 2:  **Active Directory Domains and Trusts** right click choose **Properties**
![](images/image2.jpg)
Step 3: Type *UPN suffix* domain in Alternative UPN suffixes:
![](images/image3.jpg)
Step 4: Then **Apply**, **OK**.
![](images/image4.jpg)

#### Powershell
Step 1: Run as Administrator, and type command:
                    
> Set-ADForest -Identity cpehcm.com -UPNSuffixes @{Add="cpehcm.biz"}
                    
![](images/image5.jpg)
Step 2: List all UPN suffixes domain via Powershell command:
                    
>Get-ADForest | fl UPNSuffixes
                    
![](images/image6.jpg)
Step 3: Change all users to new UPN suffix domain via Powershell, for example:
                    
>Get-ADForest | Set-ADForest -UPNSuffixes @{add="cpehcm.biz"}
                    
![](images/image6.jpg)
Step 4: Change all users to new UPN suffix domain via GUI:
![](images/image7.jpg)
