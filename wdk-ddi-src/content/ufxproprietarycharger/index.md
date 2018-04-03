---
UID: NA:ufxproprietarycharger
ms.assetid: d02b3696-a339-37ca-89b4-4a16b2ccf5c4
ms.author: windowsdriverdev
ms.date: 04/03/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ufxproprietarycharger.h header


## -description


This header is used by usbref. For more information, see:

- [Universal Serial Bus (USB)](../_usbref/index.md)

## USB proprietary charger detection

During an attach operation, the lower filter can detect the port as a proprietary charger. If the lower filter wants to handle operations for that type of charger it must publish its support through the  UFX_INTERFACE_PROPRIETARY_CHARGER device interface. During the publishing process, the driver also registers its implementation of callback functions that the UFX/client driver pair invokes when it gets request for the charger.


After calling WdfDeviceCreate, the driver performs these steps
To publish support for proprietary chargers, the filter driver must perform these steps:

To support proprietary chargers, populate a UFX_INTERFACE_PROPRIETARY_CHARGER structure. Set pointers to its implementation of these callback functions.


Callback function
Description



UFX_PROPRIETARY_CHARGER_DETECT



Detects if a charger is attached  and get details about the charger.




UFX_PROPRIETARY_CHARGER_SET_PROPERTY



Set a configurable property on the charger.




UFX_PROPRIETARY_CHARGER_ABORT_OPERATION



Aborts an attach-detect operation.




UFX_PROPRIETARY_CHARGER_RESET_OPERATION



Resets a charger operation.



 

Initialize a WDF_QUERY_INTERFACE_CONFIG structure by calling WDF_QUERY_INTERFACE_CONFIG_INIT. In this call, pass the populated UFX_INTERFACE_PROPRIETARY_CHARGER structure and GUID_UFX_INTERFACE_PROPRIETARY_CHARGER as the InterfaceType value. The GUID is defined in ufxproprietarycharger.h.
Call WdfDeviceAddQueryInterface and pass the initialized WDF_QUERY_INTERFACE_CONFIG structure.



Upon detection, the UFX/client driver pair invokes the UFX_PROPRIETARY_CHARGER_DETECT callback function. The lower filter driver assigns a charger ID: a GUID that can be used to identify a specific type of charger. If a specific charger is configurable, the driver must also define a list of supported properties and their possible value types. 
UFX passes the charger ID to CAD, which passes it to the battery miniclass driver supplied by the SoC vendor or OEM.  If a specific charger is configurable, the battery miniclass driver determines the appropriate current and/or voltage levels for the charger based on the charger ID and can send  an IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY request to UFX.  UFX invokes the client driver's EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY. The client driver can handle that request or invoke the lower filter driver's UFX_PROPRIETARY_CHARGER_SET_PROPERTY callback that configures the charger.

## Related topics

Send comments about this topic to Microsoft

