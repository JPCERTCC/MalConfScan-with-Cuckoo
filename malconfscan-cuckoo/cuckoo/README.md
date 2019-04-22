# About the code
## Introduction
The code here only contains the modified and added code from [Cuckoo Sandbox 2.0.6](https://github.com/cuckoosandbox/cuckoo/releases/tag/2.0.6).

## Add new plugin into Cuckoo Sandbox 
To integrate the MalConfScan plugin into Cuckoo Sandbox, you need to add and modify some files in Cuckoo Sandbox. The following steps is same as adding a new plugin of Voloatility into Cuckoo Sandbox.

### Change basic configurations
Modify the following files to enable the new plugin.
  - $CUCKOO/cuckoo/common/config.py
  - $CUCKOO/cuckoo/compat/config.py
  - $CUCKOO/cuckoo/private/cwd/conf/memory.conf
### Add new function to process memory dump
Modify the following file to define the MalConfScan function.
  - $CUCKOO/cuckoo/processing/memory.py
### Add new web interface to report the result
Modify the following file to show the MalConfScan report into memory analysis page.
  - $CUCKOO/cuckoo/web/templates/analysis/pages/memory/index.html

And add the following file to generate the MalConfScan report.
  - $CUCKOO/cuckoo/web/templates/analysis/pages/memory/_malconfscan.html

__For MalConfScan-with-Cuckoo, you could patch your cuckoo with [malconfscan.patch](https://github.com/JPCERTCC/MalConfScan-with-Cuckoo/blob/master/malconfscan.patch) and patch command.__


For more detail, please check our [Wiki page](https://github.com/JPCERTCC/MalConfScan-with-Cuckoo/wiki).
