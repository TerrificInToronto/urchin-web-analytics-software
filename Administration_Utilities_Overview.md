# Administration Utilities Overview #

### Overview ###

Urchin ships with a number of utility programs that are used for diagnostic and configuration purposes. These utilities are located in the util directory of the Urchin distribution. This document is intended as an introductory overview of these utilities. It is not a comprehensive guide to their usage.

All utilities support "-h" and "-v" command line arguments. Invoking a utility with the "-h" argument will give a summary of usage and the available options for that tool. Invoking with "-v" argument prints the Urchin version of the utility.

### geo-update ###

This utility is used to check the updates to Urchin's internal DNS database and to download the updates if they are available. It allows you to download the updates from Google download servers as well as from some local directory (new in urchin 6).

### inspector ###

This utility performs basic checks on your installed Urchin distribution, ensuring that the overall structure of the distribution is intact, that all the binaries shipped with the product are the proper version, and that the underlying permissions are correct (on UNIX-type platforms). The utility also reports on the operational status of the Urchin Profile Schedulers (urchind), CPC Schedulers (urchincpcd, urchincpc) and the bundled Apache web server (urchinwebd). It also verifies the licensing information.

### uconf-manager (Urchin 6.402+) ###

The Urchin Configuration Manager Utility (uconf-manager) allows you to add, edit and delete db records.

  * Urchin 6.402: This utility was first introduced in Urchin 6.402 and only operated on the 'uusers' table in the configuration database. It can be used to reset the Urchin admin password, automate user creation, and move a user to a different account.
  * Urchin 6.500+: In urchin 6.5 and later versions, this utility support db operations on more tables (uaccounts, ucosts, ufilters, ugoals, ugroups, ugroups\_uusers, ulogs, ulogs\_ufilters, uprofiles, uprofiles\_ucosts, uprofiles\_ufilters, uprofiles\_ugroups, uprofiles\_ulogs, uprofiles\_uusers, and uusers). This utility can be used to perform actions that can't be accomplished via the Urchin Administration Interface.

### uconf2sql ###

Urchin 5 and older versions store configuration information in propriety files, however, Urchin 6 stores this information in a relational database (MySql or PostgreSql). To allow smooth transition of configuration information, both Urchin 5 and Urchin 6 provide utilities for exporting and importing configuration information. Urchin 5 has a utility, named uconf-export, to export the configuration database into a file (in XML format) and Urchin 6 has a utility, named uconf2sql, to import the configuration data from this XML file in to Urchin 6 database.

### convert-u5data ###

Like the configuration database, the structure of the reporting database (that stores reporting information) has also been changed in Urchin 6. This utility, convert-u5data, provides an option for importing the reporting database directly from Urchin 5 installation into the urchin 6 installation.

### udb-sanitizer ###

The udb-sanitizer utility is used to perform management related operations on the reporting database. This includes reverting back to an archived database, deleting information about a specific date or range of dates (in case reprocessing is required).

### urchinctl ###

(Note: this utility lives in the bin directory, not the util directory). This utility provides a means of starting and stopping the Urchin Scheduler and Urchin Webserver services. On UNIX-type systems, urchinctl is typically called from one of the system's boot-time scripts to automatically start up or shut down Urchin services. On windows platform it also provides options for installing and uninstalling the urchin services.

### urchincpc (Urchin 6.5+) ###

(Note: this utility lives in the bin directory, not the util directory). The Urchin CPC Data Importing tool extracts CPC data through Google AdWords API for further processing and reporting. For more information, see [CPC Data Import Utilities](https://secure.urchin.com/helpwiki/en/CPC_Data_Import_Utilities).

### urchincpcd (Urchin 6.5+) ###

(Note: this utility lives in the bin directory, not the util directory). The Urchin CPC Source Scheduler (or simply CPC Scheduler) is used to schedule CPC download tasks based on a user defined schedule (similar to the Profile Scheduler). For more information, see [CPC Data Import Utilities](https://secure.urchin.com/helpwiki/en/CPC_Data_Import_Utilities).

### urchin\_daemons ###

On UNIX-type machines Urchin runs a scheduler daemon (urchind) and an Apache webserver (urchinwebd). These programs should be started at boot time. The urchin\_daemons script can be added to the system initialization scripts in the location appropriate for your UNIX-type OS, and it will cause the Urchin service daemons to be launched properly. On windows platforms, these binaries run as system services and can be started and stopped using windows service manager.

### ugetlicense ###

The Urchin License Operation Utility, ugetlicense, allows you to perform operations on a serial number. These operations will be necessary if a current Urchin installation becomes unavailable and needs to be reinstalled or migrated to a different server, etc.


### autoupdate (Urchin 7+) ###
The autoupdate utility is used to check for, download, and install available Urchin component updates.

Operations that autoupdate can perform are:
  * automatic upgrades of Urchin components such as the Urchin product, Embedded Help, Help Center documentation and Geo database.
  * rollback of an upgrade process if there are errors.