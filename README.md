# SPOFlatFile
## Details
This repo is intended to hold code that will produce a snapshot of the tenant configuration at a moment in time. The output of the code will be a flat file that documents specific configuration components. I will be able to use this code to  script a regular backup of the tenant configuration, as well as to publish specific documentation

## Next Steps
- Review the PowerShell cmdlets for SPO to ID the ones that might be useful
- Review the initial MSFT configuration files to determine what information they included - honestly this will probably be the best V1 architecture we can devise

### Next Next Steps
- A plan to account for specifically configured sites in the tooling - this may require a master list of specifically configured sites 

### Other Considerations
The initial draft of this work will be done in PowerShell. I think it will be interesting to see if I can eventually do all the same things in Python over time. 

## Concerns
Utilizing these scripts could constiture a security risk - for instance, we need to discuss where these files should be stored. Providing a detailed configuration could be considered similar to providing the layout of the tenant - a pathway through which an adversary could craft an attack or persistence vector.

Utimately, I don't give a shit - I'm a dev
