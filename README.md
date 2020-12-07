This Workflow will upload your Outbank exports to YNAB

If properly configured the workflow runs on Oubank export files added to the specified folder and upload the transactions to the corresponding YNAB accounts. 


Requirements:
* https://github.com/borsboom/cli-for-ynab 
* https://github.com/wireservice/csvkit (brew install csvkit)
* https://github.com/johnkerl/miller (brew install miller)


How to use:
1. Copy the workflow to your `~/Library/Workflows/Applications/Folder Actions` folder
2. Create a folder for the Outbank exports and add the workflow for this folder
3. Run `ynab list accounts` in the terminal and save the account ids - you will need them in the next step
4. Create a local mapping file `~/.ynab_accounts_mapping.csv` with the account id mapping. It has to contain at least the account numbers of your bank accounts and the corresponding account ids from YNAB

```
ACCOUNT_NUMBER;YNAB_ACCOUNT_ID
DE69123456789123456789;xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
DE69123456789123456789;xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Only transactions of the accounts listed in this file will be uploaded to YNAB. Already uploaded transactions will be skipped.
