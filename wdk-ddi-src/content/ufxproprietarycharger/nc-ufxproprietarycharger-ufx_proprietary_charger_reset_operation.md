---
UID: NC:ufxproprietarycharger.UFX_PROPRIETARY_CHARGER_RESET_OPERATION
title: UFX_PROPRIETARY_CHARGER_RESET_OPERATION
author: windows-driver-content
description: The filter driver's implementation to reset a charger operation.
old-location: buses\ufx_proprietary_charger_reset_operation.htm
tech.root: usbref
ms.assetid: F307A139-B55A-4C29-BE2F-14C243115F8C
ms.date: 5/7/2018
ms.keywords: PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION, PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION callback function pointer [Buses], UFX_PROPRIETARY_CHARGER_RESET_OPERATION, UFX_PROPRIETARY_CHARGER_RESET_OPERATION callback, UfxProprietaryChargerReset, UfxProprietaryChargerReset callback function [Buses], buses.ufx_proprietary_charger_reset_operation, ufxproprietarycharger/UfxProprietaryChargerReset
ms.topic: callback
req.header: ufxproprietarycharger.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ufxproprietarycharger.h
api_name:
-	PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# UFX_PROPRIETARY_CHARGER_RESET_OPERATION callback function


## -description


The filter driver's implementation to reset a charger operation.


## -parameters




### -param Context [in]

    A pointer to a driver-defined context.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



To support handling of proprietary chargers, the USB lower filter driver must publish support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>.




## -see-also




<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>
 

 

