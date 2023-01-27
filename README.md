### REFrameWork Template ###
**Robotic Linear Framework**

* Built on top of *Transactional Business Process* template
* Uses *Linear Sequence* layout for the phases of automation project
* Offers high level logging and exception handling
* Keeps external settings in *Config.xlsx* file and Orchestrator assets
* Pulls credentials from Orchestrator assets and *Windows Credential Manager*
* Gets transaction data from Orchestrator queue and updates back status
* Takes screenshots in case of system exceptions

### How It Works ###

 + ./Framework/*InitiAllSettings* - Load configuration data from Config.xlsx file and from assets
 + ./Framework/*GetAppCredential* - Retrieve credentials from Orchestrator assets or local Windows Credential Manager
 + ./Framework/*InitiAllApplications* - Open and login to applications used throughout the process
 + ./Framework/*Process* - Process trasaction and invoke other workflows related to the process being automated 
 + ./Framework/*CloseAllApplications* - Logs out and closes applications used throughout the process

### For New Project ###

1. Check the Config.xlsx file and add/customize any required fields and values
2. Implement InitiAllApplications.xaml and CloseAllApplicatoins.xaml workflows, linking them in the Config.xlsx fields
3. Implement Process.xaml workflow and invoke other workflows related to the process being automated
