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
CYW43455             1MW                1LC, 1HK            SDIO          802.11a/b/g/n/ac		1MW - Mass Market; 1LC, 1HK - Strategic customer engagement only.
CYW4373              2AE                N/A		    SDIO, USB     802.11a/b/g/n/ac
CYW4373              2BC                N/A		    SDIO          802.11a/b/g/n/ac
CYW43012             1LV                N/A                 SDIO          802.11a/b/g/n/ac-friendly	"802.11ac friendly"; MAX 20 MHz Bandwidth.
CYW43022             2GF                N/A                 SDIO          802.11a/b/g/n/ac-friendly	"802.11ac friendly"; MAX 20 MHz Bandwidth.
CYW43430/CYW4343W    1DX                1LN                 SDIO          802.11b/g/n
CYW43439             1YN                N/A		    SDIO          802.11b/g/n
CYW43364             1FX                N/A                 SDIO          802.11b/g/n			Same WLAN core as 1DX.
CYW43340/CYW43341    1BW                N/A                 SDIO          802.11b/g/n			Legacy module; No longer supported.
CYW55573             2EA                N/A                 PCIe, SDIO    802.11a/b/g/n/ac/ax
CYW55513             2FY/2GY                N/A                 SDIO          802.11a/b/g/n/ac/ax

========================================================================================================================
File Name                                                                        |    md5sum          		       |
=================================================================================|=====================================|
BCM43012C0_003.001.015.0303.0267.1LV.sAnt.hcd                   	         | 785a7641770124e93e0b9880a354f6ef    |
BCM43012C0_003.001.015.0300.0266.1LV.dAnt.hcd 	                                 | 055da4b08c05dd096a8d9f38cfcdb96a    |
CYW43012C1_003.002.024.0036.0008.2GF.hcd                                         | 7b1777f2303ee9ff32f86e5a748c0266    | 
BCM43430A1_001.002.009.0159.0528.1DX.hcd	                                 | 6a8ec1963a5d1da4ae4287ff1047d751    |
BCM4345C0_003.001.025.0187.0366.1MW.hcd	                                         | bf85a2a431ac4498ba7d39561c402c25    |
BCM43012C0_003.001.015.0303.0267.1LV.sAnt.hcd	                                 | 2e13cc32f6d0dafc6aeb05cbd77124c4    |
BCM43012C0_003.001.015.0300.0266.1LV.dAnt.hcd	                                 | 9352731b9b8c2370d5430318568e9570    |
BCM4359D0_004.001.016.0241.0275.1XA.sAnt.hcd                                     | fdc2cf455c94d72f81638f9c8c9e7fd3    |
BCM4359D0_004.001.016.0241.0274.1XA.dAnt.hcd                                     | f84b3c53150bb26422e2a37e2a5b8efa    |
BCM4359D0_004.001.016.0241.0275.2BZ.sAnt.hcd                                     | fdc2cf455c94d72f81638f9c8c9e7fd3    |
BCM4359D0_004.001.016.0241.0274.2BZ.dAnt.hcd                                     | f84b3c53150bb26422e2a37e2a5b8efa    |
CYW4343A2_001.003.016.0071.0017.1YN.hcd	                                         | 0c050437ed2ed6f9c451b7732e7729ef    |
CYW43341B0.1BW.hcd	                                                         | 54d140ac2503c5d34631cb30c4c3657e    |
CYW55560A1_001.002.087.0269.0100.FCC.2EA.sAnt.hcd                                | 2ef2b4ea2c77d8d29ee27fd55129b384    |
CYW55560A1_001.002.087.0269.0103.FCC.2EA.dAnt.hcd                                | e068e64325b45596d410cae2b02fe410    |
CYW55560A1_001.002.087.0269.0106.EU.JP.2EA.sAnt.hcd                              | 5e1375b80fda2cb551945341493cc716    |
CYW55560A1_001.002.087.0269.0107.EU.JP.2EA.dAnt.hcd                              | 9cac705f13c0c023fb24862164135190    |
CYW55500A1_001.002.032.0040.0033.2FY.hcd                                         | e43ce2141f4ddadc0a4a6233fb583900    |
CYW55500A1_001.002.032.0040.0032.CE.JP.2FY.2GY.hcd                               | 584e5a881cc2e48d30bee83502d821c4    |
CYW55500A1_001.002.032.0040.0033.FCC.2FY.2GY.hcd                                 | e43ce2141f4ddadc0a4a6233fb583900    |
BCM4373A0_001.001.025.0103.0275.UART.PCM1.JRL.2AE.hcd                            | d640b755036bf2c1737c2d6c058223c5    |
BCM4373A0_001.001.025.0103.0276.UART.PCM1.FCC.CE.2AE.hcd                         | 698c89057ab299bd4a7346e10ea34a1c    |
BCM4373A0_001.001.025.0119.0261.USB.PCM1.FCC.CE.2AE.hcd                          | 926b07e9869d70a8ca196da399795370    |
BCM4373A0_001.001.025.0119.0262.USB.PCM1.JRL.2AE.hcd                             | d7a103c0e27982c7ef499e25b98e4523    |
========================================================================================================================
