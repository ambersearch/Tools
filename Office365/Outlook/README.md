# Getting shared mailboxes and permissions

This script is designed to generate .csv file with shared mailbox permission report.

## Script Highlights: 
- The script display only **“Explicitly assigned permissions”** to mailboxes which means it will ignore “SELF” permission that each user on his mailbox and inherited permission. 
- Exports output to **CSV** file. 
- The script can be executed with **MFA enabled account** also. 
- You can choose to either “export permissions of all mailboxes” or pass an input file to **get permissions of specific mailboxes** alone. 
- Allows you to filter output using your desired permissions like **Send-as, Send-on-behalf** or **Full access**. 
- This script is **scheduler friendly**. I.e., credentials can be passed as a parameter instead of saving inside the script 

## Export Shared Mailbox Permission Report Using PowerShell: 

To execute the script with MFA enabled account or non-MFA account, use the below format from the powershell windows with administrative privileges. Administrative privileges are needed only during first run to install the dependencies. 

```l
./GetSharedMailboxPermissions.ps1
```

After script startup login page will appear. Please login with outlook administrative account.

## Additional information:

Additional information and use cases can be found here: https://o365reports.com/2020/01/03/shared-mailbox-permission-report-to-csv/

## Known issues

Sometimes script sign error can occur preventing form executing unsigned scripts. 

<img src="https://github.com/ambersearch/Tools/assets/44996098/e9dcd605-205d-496a-b6ae-8dab1f10be3f" height="100px" />


To solve this issue you can temporary or permanently change current security policy.

To check current policy following command can be used in PowerShell **with administrative rights**. 

```powershell
Get-ExecutionPolicy -List
```

You will see something like this:
<img src="https://github.com/ambersearch/Tools/assets/44996098/226894eb-9a33-4390-a138-b42c35406374" height="200px" />

To change current execution policy:

```powershell
Set-ExecutionPolicy -Scope  LocalMachine -ExecutionPolicy bypass
```

More info: https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.4
