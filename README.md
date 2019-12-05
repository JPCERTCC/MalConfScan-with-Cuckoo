<div align="center"><img src="img/title.png" width=80%></div>

## Introduction

[__MalConfScan__](https://github.com/JPCERTCC/MalConfScan) integration for [__Cuckoo Sandbox__](https://github.com/cuckoosandbox/cuckoo).<br>
This plugin lets you integrate MalConfScan into Cuckoo Sandbox with the patch file. The plugin would add the function to extract known malware's configuration data from memory dump and, add the MalConfScan report into Cuckoo Sandbox.<br><br>

### Sample report

#### Screenshot: Sample report of [Himawari (a variant of RedLeaves)](https://blogs.jpcert.or.jp/en/2017/04/redleaves---malware-based-on-open-source-rat.html) in Cuckoo

![Himawari Cuckoo](https://raw.githubusercontent.com/JPCERTCC/MalConfScan-with-Cuckoo/master/img/himawari-cuckoo.png)

#### Sample `report.json`

```json
...snip...
"malconfscan": {
    "data": [
        {
            "malconf": [
                [
                    {"Server1": "diamond.ninth.biz"}, 
                    {"Server2": "diamond.ninth.biz"}, 
                    {"Server3": "diamond.ninth.biz"}, 
                    {"Server4": "diamond.ninth.biz"}, 
                    {"Port": "443"}, 
                    {"Mode": "TCP and HTTP"}, 
                    {"ID": "2017-11-28-MACRO"}, 
                    {"Mutex": "Q34894iq"}, 
                    {"Key": "usotsuki"}, 
                    {"UserAgent": "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; WOW64; Trident/4.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; .NET4.0C; .NET4.0E)"}, 
                    {"Proxy server": ""}, 
                    {"Proxy username": ""}, 
                    {"Proxy password": ""}
                ]
            ], 
            "vad_base_addr": "0x04521984", 
            "process_name": "iexplore.exe", 
            "process_id": "2248", 
            "malware_name": "Himawari", 
            "size": "0x00815104"
        }
    ],
},
...snip...
```

## What's MalConfScan?

MalConfScan is a [Volatility](https://github.com/volatilityfoundation/volatility) plugin extracts the configuration data of known malware. It supports 20+ malware families. Check the detail [here](https://github.com/JPCERTCC/MalConfScan/wiki).

## How to install

Modify the source code of Cuckoo Sandbox with the deploy-script and deploy Cuckoo Sandbox. If you want to know more detail, please check the [Wiki](https://github.com/JPCERTCC/MalConfScan-with-Cuckoo/wiki).

## How to use

1. Setup your Cuckoo Sandbox and patch it with `malconfscan.patch`.
2. Submit your sample to the sandbox.
3. Check the report.

## Overview & Demonstration

  Following [YouTube video](https://youtu.be/2K8Vh0XqG24) shows the overview of MalConfScan with Cuckoo.

  [![MalConfScan-with-Cuckoo_Overview](https://img.youtube.com/vi/2K8Vh0XqG24/sddefault.jpg)](https://youtu.be/2K8Vh0XqG24)

  And, following  [YouTube video](https://youtu.be/754NnYWJo_s) is the demonstration of MalConfScan with Cuckoo.

  [![MalConfScan-with-Cuckoo_Demonstration](https://img.youtube.com/vi/754NnYWJo_s/sddefault.jpg)](https://youtu.be/754NnYWJo_s)

## Notes

Tested with following environments.
 - Python 2.7.15
 - Cuckoo Sandbox 2.0.6
 - Volatility 2.6
