SSRS_ReportBackup 
========

This is a script for Microsoft SQL Report Server rs.exe that can be used to back up all report layouts that are in a specific Report Server folder.

To run the script, you must specify the global variables parentPath and exportTo as an argument to rs.exe by using the -v switch.

Usage
-----

```
rs -i ReportBackup.rss -s http://localhost:8080/ReportServer -v parentPath="/" -v exportTo=".\Export"
```

* parentPath	Set this to the parent folder in SSRS that you wish to back up. For example, setting this to "/" will back up all reports in all sub folders.
* exportTo		Set this to the directory on disk where you want to back up the report .RDL files, without any trailing slash.
			The structure on disk will match the structure in ssrsPath.

Logging
-----

Right now, this script creates two log files, ReportBackup.log and Error.log.

ReportBackup.log will log which report is exported and where the report is exported.

Error.log will contain any exceptions that are encountered during the execution of the script.
