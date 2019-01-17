---
UID: NS:ufxproprietarycharger._UFX_INTERFACE_PROPRIETARY_CHARGER
title: "_UFX_INTERFACE_PROPRIETARY_CHARGER"
description: Stores pointers to driver-implemented callback functions for handling proprietary charger operations.
old-location: buses\ufx_interface_proprietary_charger.htm
tech.root: usbref
ms.assetid: 3E75EA87-FBF8-4FFB-9CD7-F8E1D5353D68
ms.date: 05/07/2018
ms.keywords: "*PUFX_INTERFACE_PROPRIETARY_CHARGER, PUFX_INTERFACE_PROPRIETARY_CHARGER, PUFX_INTERFACE_PROPRIETARY_CHARGER structure pointer [Buses], UFX_INTERFACE_PROPRIETARY_CHARGER, UFX_INTERFACE_PROPRIETARY_CHARGER structure [Buses], _UFX_INTERFACE_PROPRIETARY_CHARGER, buses.ufx_interface_proprietary_charger, ufxproprietarycharger/PUFX_INTERFACE_PROPRIETARY_CHARGER, ufxproprietarycharger/UFX_INTERFACE_PROPRIETARY_CHARGER"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ufxproprietarycharger.h
api_name:
-	UFX_INTERFACE_PROPRIETARY_CHARGER
product:
- Windows
targetos: Windows
req.typenames: UFX_INTERFACE_PROPRIETARY_CHARGER, *PUFX_INTERFACE_PROPRIETARY_CHARGER
---

# _UFX_INTERFACE_PROPRIETARY_CHARGER structure


## -description


Stores pointers to driver-implemented callback functions for handling proprietary charger operations.


## -struct-fields




### -field InterfaceHeader

The interface version number.


### -field ProprietaryChargerDetect

A pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187981">UFX_PROPRIETARY_CHARGER_DETECT</a> callback function.


### -field ProprietaryChargerSetProperty

A pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187983">UFX_PROPRIETARY_CHARGER_SET_PROPERTY</a> callback function.


### -field ProprietaryChargerAbortOperation

A pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187980">UFX_PROPRIETARY_CHARGER_ABORT_OPERATION</a> callback function.


### -field ProprietaryChargerResetOperation

A pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187982">UFX_PROPRIETARY_CHARGER_RESET_OPERATION</a> callback function.


## -see-also




<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>
 

 

