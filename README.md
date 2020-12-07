This Workflow will upload your Outbank exports to YNAB

If properly configured the workflow runs on Oubank export files added to the specified folder and upload the transactions to the corresponding YNAB accounts. Already uploaded transactions will be skipped.


Requirements:
- https://github.com/borsboom/cli-for-ynab 
- https://github.com/wireservice/csvkit (brew install csvkit)
- https://github.com/johnkerl/miller (brew install miller)


How it works:
The workflow uses csvkit and miller for converting the exported file to the upload-ready JSON format. You have to adjust some code here:
- edit the filter section to include accounts you want to be synchronized
- edit the 'sed' section for replacing the account ids with their YNAB specific counterparts (you will need to run ynab list accounts to get your account ids from YNAB)

You can check the script result in the system log console (filter for the "logger" process)
