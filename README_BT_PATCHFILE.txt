THE FOLLOWING NOTES APPLY ONCE THE YOCTO LINUX IMAGE IS BUILT AND ROOTFS IS POPULATED:
======================================================================================
Use "murata-master" sub-folder for module-specific Bluetooth patchfiles. When executing "hciattach" in Linux, the BlueZ stack queries 
the BT core for a chip ID (over UART connection) which it uses for loading the corresponding Bluetoothpatchfile from "/etc/firmware" folder. 
The hcd files are renamed from CYW43XX to BCM43XX.

Files in sub-folder "murata-master" will have symbol "_" infront of the file name.
Ex: BCM43430A1.1DX.hcd will be named as _BCM43430A1.1DX.hcd
User will have to remove "_" and copy it to /etc/firmware. 

NOTE: this Bluetooth patchfiles (*.hcd) are intended as reference only. The user needs to customize the Bluetooth patchfile to meet their HW/SW system requirements. 

Cypress Chipset	     Default		Options		WLAN Interface    Devices Supported	  	    Notes
===============	     =======		=======		==============    =====================   	===============================================================
CYW54591             1XA                N/A	            PCIe          802.11a/b/g/n/ac MIMO
CYW4356              1CX                N/A	            PCIe          802.11a/b/g/n/ac MIMO
CYW4354              1BB                N/A                 SDIO          802.11a/b/g/n/ac MIMO		Strategic customer engagement only.
CYW43455             1MW                1LC, 1HK            SDIO          802.11a/b/g/n/ac		1MW - Mass Market; 1LC, 1HK - Strategic customer engagement only.
CYW4373              2AE                N/A		    SDIO          802.11a/b/g/n/ac
CYW4373              2BC                N/A		    SDIO          802.11a/b/g/n/ac
CYW43012             1LV                N/A                 SDIO          802.11a/b/g/n/ac-friendly	"802.11ac friendly"; MAX 20 MHz Bandwidth.
CYW43022             2GF                N/A                 SDIO          802.11a/b/g/n/ac-friendly	"802.11ac friendly"; MAX 20 MHz Bandwidth.
CYW43430/CYW4343W    1DX                1LN                 SDIO          802.11b/g/n
CYW43439             1YN                N/A		    SDIO          802.11b/g/n
CYW43364             1FX                N/A                 SDIO          802.11b/g/n			 Same WLAN core as 1DX.
CYW4339	             ZP                 1CK                 SDIO          802.11a/b/g/n/ac		 Legacy module; No longer supported.
CYW43340/CYW43341    1BW                N/A                 SDIO          802.11b/g/n			 Legacy module; No longer supported.
CYW43362             SN8000             N/A	            SDIO          802.11b/g/n			 Legacy module; No longer supported.
CYW55573             2EA                N/A                 PCIe, SDIO    802.11a/b/g/n/ac

========================================================================================================================
File Name                                                                        |    md5sum          		       |
=================================================================================|=====================================|
BCM43012C0_003.001.015.0303.0267.1LV.sAnt.hcd                   	         | 785a7641770124e93e0b9880a354f6ef    |
BCM43012C0_003.001.015.0300.0266.1LV.dAnt.hcd 	                                 | 055da4b08c05dd096a8d9f38cfcdb96a    |
CYW43012C1_003.002.024.0034.0004.2GF.hcd                                         | 3b9ef7837610ac0e6d752542fff3ed20    | 
BCM43430A1_001.002.009.0159.0528.1DX.hcd	                                 | 6a8ec1963a5d1da4ae4287ff1047d751    |
BCM4345C0_003.001.025.0187.0366.1MW.hcd	                                         | bf85a2a431ac4498ba7d39561c402c25    |
BCM4356A2_001.003.015.0112.0410.1CX.hcd		                                 | aeb5b670d21828012006eb2a5601e0f2    |
BCM43012C0_003.001.015.0303.0267.1LV.sAnt.hcd	                                 | 2e13cc32f6d0dafc6aeb05cbd77124c4    |
BCM43012C0_003.001.015.0300.0266.1LV.dAnt.hcd	                                 | 9352731b9b8c2370d5430318568e9570    |
BCM4359D0_004.001.016.0241.0275.1XA.sAnt.hcd                                     | fdc2cf455c94d72f81638f9c8c9e7fd3    |
BCM4359D0_004.001.016.0241.0274.1XA.dAnt.hcd                                     | f84b3c53150bb26422e2a37e2a5b8efa    |
BCM4359D0_004.001.016.0241.0275.2BZ.sAnt.hcd                                     | fdc2cf455c94d72f81638f9c8c9e7fd3    |
BCM4359D0_004.001.016.0241.0274.2BZ.dAnt.hcd                                     | f84b3c53150bb26422e2a37e2a5b8efa    |
BCM4373A0_001.001.025.0103.0155.FCC.CE.2AE.hcd                                   | 1e287a3ab7f83e59352cb321315ea80f    |
BCM4373A0_001.001.025.0103.0156.JRL.2AE.hcd                                      | bbdb081f5e6d75e5ca87ef3b0ccb0bf2    |
BCM4373A0_001.001.025.0103.0155.FCC.CE.2BC.hcd                                   | 1e287a3ab7f83e59352cb321315ea80f    |
BCM4373A0_001.001.025.0103.0156.JRL.2BC.hcd                                      | bbdb081f5e6d75e5ca87ef3b0ccb0bf2    |
BCM4373A0.2AE.hcd				                                 | 4788119eb154576283bb167208a1ede9    |
CYW4343A2_001.003.016.0031.0000.1YN.hcd	                                         | 4c49ef93f4ded4f7cfe10645cabb483c    |
CYW43341B0.1BW.hcd	                                                         | 54d140ac2503c5d34631cb30c4c3657e    |
CYW4335C0.ZP.hcd                                                                 | c29b894df41e1ed41f1e77d9e44f1aa0    |
CYW4350C0.1BB.hcd                                                                | d6a60d308d5ac8277c704d11149dc1c2    |
CYW55560A1_001.002.087.0269.0100.FCC.2EA.sAnt.hcd                                | 2ef2b4ea2c77d8d29ee27fd55129b384    |
CYW55560A1_001.002.087.0269.0103.FCC.2EA.dAnt.hcd                                | e068e64325b45596d410cae2b02fe410    |
CYW55560A1_001.002.087.0269.0106.EU.JP.2EA.sAnt.hcd                              | 5e1375b80fda2cb551945341493cc716    |
CYW55560A1_001.002.087.0269.0107.EU.JP.2EA.dAnt.hcd                              | 9cac705f13c0c023fb24862164135190    |
========================================================================================================================
