# Getting shared mailboxes and permissions (On-Premises Exchange)

This script is designed to generate .csv file with shared mailbox permission report for on-premises Exchange Server.

## Script Highlights: 
- The script display only **"Explicitly assigned permissions"** to mailboxes which means it will ignore "SELF" permission that each user on his mailbox and inherited permission. 
- Exports output to **CSV** file. 
- You can choose to either "export permissions of all mailboxes" or pass an input file to **get permissions of specific mailboxes** alone. 
- Allows you to filter output using your desired permissions like **Send-as, Send-on-behalf** or **Full access**. 
- This script is for **on-premises Exchange Server** environments.

## Opening Exchange Management Shell:

To run the script, you need to open Exchange Management Shell first.

Connecto to the Exchange Server via RDP:
   - Click Start
   - Find "Exchange Management Shell" in the programs list
   - Rightclick and 'Run as administrator'

## Export Shared Mailbox Permission Report Using PowerShell: 

You need to download the script and save it on the Exchange Server.

To execute the script, use the below format from the Exchange Management Shell:

```powershell
./GetSharedMailboxPermissionsOnprem.ps1
```

To filter specific permissions, use these parameters:
```powershell
./GetSharedMailboxPermissionsOnprem.ps1 -FullAccess
./GetSharedMailboxPermissionsOnprem.ps1 -SendAs
./GetSharedMailboxPermissionsOnprem.ps1 -SendOnBehalf
```

To get permissions for specific mailboxes, create a text file with mailbox names and use:
```powershell
./GetSharedMailboxPermissionsOnprem.ps1 -MBNamesFile "path\to\mailboxes.txt"
```