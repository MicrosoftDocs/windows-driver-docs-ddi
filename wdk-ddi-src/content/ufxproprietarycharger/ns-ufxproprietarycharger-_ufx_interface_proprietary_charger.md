---
UID: NS:ufxproprietarycharger._UFX_INTERFACE_PROPRIETARY_CHARGER
title: "_UFX_INTERFACE_PROPRIETARY_CHARGER"
author: windows-driver-content
description: Stores pointers to driver-implemented callback functions for handling proprietary charger operations.
old-location: buses\ufx_interface_proprietary_charger.htm
old-project: usbref
ms.assetid: 3E75EA87-FBF8-4FFB-9CD7-F8E1D5353D68
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PUFX_INTERFACE_PROPRIETARY_CHARGER, UFX_INTERFACE_PROPRIETARY_CHARGER structure [Buses], PUFX_INTERFACE_PROPRIETARY_CHARGER structure pointer [Buses], PUFX_INTERFACE_PROPRIETARY_CHARGER, UFX_INTERFACE_PROPRIETARY_CHARGER, ufxproprietarycharger/PUFX_INTERFACE_PROPRIETARY_CHARGER, _UFX_INTERFACE_PROPRIETARY_CHARGER, ufxproprietarycharger/UFX_INTERFACE_PROPRIETARY_CHARGER, buses.ufx_interface_proprietary_charger"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufxproprietarycharger.h
req.include-header: Ufxproprietarycharger.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ufxproprietarycharger.h
apiname:
-	UFX_INTERFACE_PROPRIETARY_CHARGER
product: Windows
targetos: Windows
req.typenames: "*PUFX_INTERFACE_PROPRIETARY_CHARGER, UFX_INTERFACE_PROPRIETARY_CHARGER"
req.product: Windows 10 or later.
---

# _UFX_INTERFACE_PROPRIETARY_CHARGER structure


## -description


Stores pointers to driver-implemented callback functions for handling proprietary charger operations.


## -syntax


````
typedef struct _UFX_INTERFACE_PROPRIETARY_CHARGER {
  INTERFACE                                   InterfaceHeader;
  PFN_UFX_PROPRIETARY_CHARGER_DETECT          ProprietaryChargerDetect;
  PFN_UFX_PROPRIETARY_CHARGER_SET_PROPERTY    ProprietaryChargerSetProperty;
  PFN_UFX_PROPRIETARY_CHARGER_ABORT_OPERATION ProprietaryChargerAbortOperation;
  PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION ProprietaryChargerResetOperation;
} UFX_INTERFACE_PROPRIETARY_CHARGER, *PUFX_INTERFACE_PROPRIETARY_CHARGER;
````


## -struct-fields




#### - InterfaceHeader

The interface version number.


#### - ProprietaryChargerDetect

A pointer to the driver's implementation of the <a href="..\ufxproprietarycharger\nc-ufxproprietarycharger-ufx_proprietary_charger_detect.md">UFX_PROPRIETARY_CHARGER_DETECT</a> callback function.


#### - ProprietaryChargerSetProperty

A pointer to the driver's implementation of the <a href="..\ufxproprietarycharger\nc-ufxproprietarycharger-ufx_proprietary_charger_set_property.md">UFX_PROPRIETARY_CHARGER_SET_PROPERTY</a> callback function.


#### - ProprietaryChargerAbortOperation

A pointer to the driver's implementation of the <a href="..\ufxproprietarycharger\nc-ufxproprietarycharger-ufx_proprietary_charger_abort_operation.md">UFX_PROPRIETARY_CHARGER_ABORT_OPERATION</a> callback function.


#### - ProprietaryChargerResetOperation

A pointer to the driver's implementation of the <a href="..\ufxproprietarycharger\nc-ufxproprietarycharger-ufx_proprietary_charger_reset_operation.md">UFX_PROPRIETARY_CHARGER_RESET_OPERATION</a> callback function.


## -see-also

<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UFX_INTERFACE_PROPRIETARY_CHARGER structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

