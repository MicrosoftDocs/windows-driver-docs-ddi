---
UID: NC:ufxproprietarycharger.UFX_PROPRIETARY_CHARGER_RESET_OPERATION
title: UFX_PROPRIETARY_CHARGER_RESET_OPERATION
author: windows-driver-content
description: The filter driver's implementation to reset a charger operation.
old-location: buses\ufx_proprietary_charger_reset_operation.htm
old-project: UsbRef
ms.assetid: F307A139-B55A-4C29-BE2F-14C243115F8C
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION, PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION callback function pointer [Buses], UFX_PROPRIETARY_CHARGER_RESET_OPERATION, UfxProprietaryChargerReset, UfxProprietaryChargerReset callback function [Buses], buses.ufx_proprietary_charger_reset_operation, ufxproprietarycharger/UfxProprietaryChargerReset
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ufxproprietarycharger.h
apiname:
-	PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION
product: Windows
targetos: Windows
req.typenames: UFX_ENDPOINT_CALLBACKS, *PUFX_ENDPOINT_CALLBACKS
req.product: Windows 10 or later.
---

# UFX_PROPRIETARY_CHARGER_RESET_OPERATION callback


## -description


The filter driver's implementation to reset a charger operation.


## -prototype


````
UFX_PROPRIETARY_CHARGER_RESET_OPERATION UfxProprietaryChargerReset;

NTSTATUS UfxProprietaryChargerReset(
  _In_ PVOID Context
)
{ ... }

typedef UFX_PROPRIETARY_CHARGER_RESET_OPERATION PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION;
````


## -parameters




### -param Context [in]

    A pointer to a driver-defined context.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



To support handling of proprietary chargers, the USB lower filter driver must publish support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>.




## -see-also

<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UFX_PROPRIETARY_CHARGER_RESET_OPERATION callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

