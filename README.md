# SPOFlatFile

## Details

This is not a functional code repo yet, pls ignore.

This repo is intended to hold code that will produce a snapshot of the tenant configuration at a moment in time. The output of the code will be a flat file that documents specific configuration components. I will be able to use this code to  script a regular backup of the tenant configuration, as well as to publish specific documentation

## Review

### Teams Policies and Configuration - From the Document

2.5 - Teams Policies and Configuration
2.5.1 - Global Configuration
2.5.2 - Teams Settings in Services
2.5.3 - Teams Policies
2.5.4 - Devices - Phones
2.5.5 - Locations
2.5.5.1 - Reporting Labels
2.5.5.2 - Emergency Locations
2.5.5.3 - Network Topology
2.5.5.4 - Networks and Locations
2.5.6 - Meetings
...
2.5.7 - Messaging Policies
2.5.8 - Teams Apps
2.5.8.1 - App Permission Policies
2.5.8.2 - App Setup Policies
2.5.9 - Voice
2.5.10 - Policy Packages
2.5.11 - Analytics and Reports
2.5.12 - Org-Wide Settings
2.5.12.1 - External Access
2.5.12.2 - Teams Settings
2.5.12.3 - Teams Upgrade
2.5.12.4 - Holidays
2.5.12.5 - Resource Accounts
2.5.13 - Microsoft 365 Groups and Additional Settigns
2.5.13.1 - Teams Lifecycle
2.5.13.2 - Teams Names
2.5.13.3 - Data Classification
2.5.13.4 - Retention

### Notes on the Teams Policy Configurations

Much of the Teams platform is described by "policies" that are applied to users within the Tenant. This makes it important not just to define the configuration of the policy, but some information on how it is applied, as well. 

### SharePoint Online Admin

Reviewing my Dev Tenant to determine what configuration settings are exposed through the UI as a way to help ID other potential information we might want to capture.

- Sites
  - Active Sites
  - Deleted Sites
- Policies
  - Sharing
  - Access Control
  - NB - I think that each toggle in this section should be captured in an export - work to ID the specific PowerShell commands for each of these items
- Settings
  - Default Admin Center
  - Home Site
  - Notifications
  - Pages
  - Site Creation
  - Site Storage Limits
  - Stream - App Launcher Title
  - OneDrive - Notifications
  - OneDrive - Retention
  - OneDrive - Storage Limit
  - OneDrive - Sync
- Content Services
  - Term Store
  - Content Type Gallery
    - Unfortunately, I think that this is going to be a big part of what we will do - publishing content types to incorporate into solutions
    - It will end up as a great example of why we need cross functionality for engineers, even if we also need someone to be the key POC for environment configurations as well
    - We should also pull backups of content types pretty regularly
- Term Store
- User Profiles
- Search
- Apps
- BCS
- Secure Store
- Records Management
- Hybrid Picker

## Next Steps

- Review the PowerShell cmdlets for SPO to ID the ones that might be useful
- Review the initial MSFT configuration files to determine what information they included - honestly this will probably be the best V1 architecture we can devise

### Next Next Steps

- A plan to account for specifically configured sites in the tooling - this may require a master list of specifically configured sites

### Potential Files to Add

- List of Connected/Approved Apps
- Export Script
- Update Script -Restores a previous version of a configuration - User must specify what component they are restoring
- Nightly Backup Script that writes the files to the appropriate location

### Other Considerations

The initial draft of this work will be done in PowerShell. I think it will be interesting to see if I can eventually do all the same things in Python over time.

## SharePoint Online Configuration Settings to Capture

## Global Settings to Capture

- DLP Policy Description and Application
- Guest Access Policy Description and Application

## Notes

- All export in the CommonSPConfig comes out to XML

This suggests to me that we might need to build a 'map' of these files - determine what is required to relate to one another.

## Questions

- I assume there are no ULS logs in this situation. Is there an equivalent? (My prediction is that there is, but they are anonymized and we have to pay microsoft to read them)

## Concerns

Utilizing these scripts could constiture a security risk - for instance, we need to discuss where these files should be stored. Providing a detailed configuration could be considered similar to providing the layout of the tenant - a pathway through which an adversary could craft an attack or persistence vector.

Utimately, I don't give a shit - I'm a dev
