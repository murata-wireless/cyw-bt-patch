THE FOLLOWING NOTES APPLY ONCE THE YOCTO LINUX IMAGE IS BUILT AND ROOTFS IS POPULATED:
======================================================================================
Use "murata-master" sub-folder for module-specific Bluetooth patchfiles. When executing "hciattach" in Linux, the BlueZ stack queries 
the BT core for a chip ID (over UART connection) which it uses for loading the corresponding Bluetoothpatchfile from "/etc/firmware" folder. 
The hcd files are renamed from CYW43XX to BCM43XX.

Files in sub-folder "murata-master" will have symbol "_" infront of the file name.
Ex: BCM43430A1.1DX.hcd will be named as _BCM43430A1.1DX.hcd
User will have to remove "_" and copy it to /etc/firmware. 

NOTE: this Bluetooth patchfiles (*.hcd) are intended as reference only. The user needs to customize the Bluetooth patchfile to meet their HW/SW system requirements. 

Cypress Chipset		Default		Options		WLAN Interface    Devices Supported	  	Notes
===============		=======		=======		==============    =====================   	===============================================================
CYW54591		1XA		N/A		PCIe              802.11a/b/g/n/ac MIMO
CYW4356			1CX		N/A		PCIe              802.11a/b/g/n/ac MIMO
CYW4354			1BB		N/A             SDIO              802.11a/b/g/n/ac MIMO		Strategic customer engagement only.
CYW43455		1MW		1LC, 1HK        SDIO              802.11a/b/g/n/ac		1MW - Mass Market; 1LC, 1HK - Strategic customer engagement only.
CYW4373                 2AE		N/A		SDIO              802.11a/b/g/n/ac
CYW4373                 2BC		N/A		SDIO              802.11a/b/g/n/ac
CYW43012		1LV		N/A             SDIO              802.11a/b/g/n/ac-friendly	"802.11ac friendly"; MAX 20 MHz Bandwidth.
CYW43430/CYW4343W	1DX		1LN             SDIO              802.11b/g/n
CYW43439                1YN		N/A		SDIO              802.11b/g/n
CYW43364                1FX             N/A             SDIO              802.11b/g/n			Same WLAN core as 1DX.
CYW4339			ZP		1CK             SDIO              802.11a/b/g/n/ac		Legacy module; No longer supported.
CYW43340/CYW43341	1BW		N/A             SDIO              802.11b/g/n			Legacy module; No longer supported.
CYW43362		SN8000		N/A	        SDIO              802.11b/g/n			Legacy module; No longer supported.


=======================================================================================
File Name					|	md5sum			      |
================================================|=====================================|
BCM43012C0_003.001.015.0230.0237.1LV.sAnt.hcd 	| 2e13cc32f6d0dafc6aeb05cbd77124c4    |
BCM43012C0_003.001.015.0240.0243.1LV.dAnt.hcd 	| 9352731b9b8c2370d5430318568e9570    |
BCM4343A1_001.002.009.0153.0520.1DX.hcd		| 328e28579ee5dbf4158c20ecb8c09c23    |
BCM4345C0_003.001.025.0172.0344.1MW.hcd		| b151a1c6de6c75c104735e5d6c736011    |
BCM4356A2_001.003.015.0112.0410.1CX.hcd		| aeb5b670d21828012006eb2a5601e0f2    |
BCM4359D0_004.001.016.0223.0231.1XA.sAnt.hcd	| a925e5e73454e0536be9a0f64a6fa5eb    |
BCM4359D0_004.001.016.0223.0230.1XA.dAnt.hcd	| 353439723c588daa53882d70fea4a19c    |
BCM4373A0.2AE.hcd				| 4788119eb154576283bb167208a1ede9    |
CYW4343A2_001.003.016.0031.0000.1YN.hcd	        | 4c49ef93f4ded4f7cfe10645cabb483c    |
CYW43341B0.1BW.hcd				| 54d140ac2503c5d34631cb30c4c3657e    |
CYW4335C0.ZP.hcd				| c29b894df41e1ed41f1e77d9e44f1aa0    |
CYW4350C0.1BB.hcd				| d6a60d308d5ac8277c704d11149dc1c2    |
=======================================================================================
