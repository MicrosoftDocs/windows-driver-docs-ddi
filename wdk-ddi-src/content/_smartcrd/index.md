---
UID: TP:smartcrd
ms.assetid: 1f409c41-e10c-39aa-8408-18629cc1c604
ms.author: windowsdriverdev
ms.date: 04/20/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Smartcard device drivers



Overview of the Smartcard device drivers technology.

To develop Smartcard device drivers, you need these headers:

 * [scutil.h](..\scutil\index.md)
 * [smcdbg.h](..\smcdbg\index.md)
 * [smclib.h](..\smclib\index.md)
 * [smcnt.h](..\smcnt\index.md)

For the programming guide, see [Smartcard device drivers](https://docs.microsoft.com/en-us/windows-hardware/drivers/smartcard).

Reference guide for developing drivers for smart card reader devices. For information about vendor-specific IOCTL operations, see RDF_IOCTL_VENDOR. 
The callback functions listed below can be implemented in a  vendor-supplied reader driver. A reader driver makes these callback functions available for the smart card library routine, SmartcardDeviceControl, to call by storing pointers to them in the smart card device extension. The pointers are stored in an array of function pointers located in the ReaderFunction member of the smart card device extension, SMARTCARD_EXTENSION. 
Individual callback functions are identified by a series of constant values that should be used as indexes into the ReaderFunction array. This includes the following callback functions:


RDF_ATR_PARSE




RDF_CARD_EJECT




RDF_CARD_POWER




RDF_CARD_TRACKING




RDF_IOCTL_VENDOR




RDF_READER_SWALLOW




RDF_SET_PROTOCOL




RDF_TRANSMIT




In this section


Topic
Description




Smart Card Driver Callback Functions



The callback functions that a vendor-supplied reader driver can implement. A reader driver makes these callback functions available for the smart card library routine, SmartcardDeviceControl, to call by storing pointers to them in the smart card device extension. The pointers are stored in an array of function pointers located in the ReaderFunction member of the smart card device extension, SMARTCARD_EXTENSION. 





Smart Card Driver Structures



These data structures are used by the smart card driver  routines and by the smart card driver callback functions.





Smart card reader device reference in SDK header files



This section lists header files and reference used in drivers for smart card reader devices. The header files in this section are included in the Windows Software Development Kit (SDK).



 


Send comments about this topic to Microsoft

