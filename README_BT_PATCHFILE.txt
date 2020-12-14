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
CYW43012		1LV		N/A             SDIO              802.11a/b/g/n/ac-friendly	"802.11ac friendly"; MAX 20 MHz Bandwidth.
CYW43430/CYW4343W	1DX		1LN             SDIO              802.11b/g/n
CYW43364                1FX             N/A             SDIO              802.11b/g/n			Same WLAN core as 1DX.
CYW4339			ZP		1CK             SDIO              802.11a/b/g/n/ac		Legacy module; No longer supported.
CYW43340/CYW43341	1BW		N/A             SDIO              802.11b/g/n			Legacy module; No longer supported.
CYW43362		SN8000		N/A	        SDIO              802.11b/g/n			Legacy module; No longer supported.

