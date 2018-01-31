---
UID: NC:ufxproprietarycharger.UFX_PROPRIETARY_CHARGER_DETECT
title: UFX_PROPRIETARY_CHARGER_DETECT
author: windows-driver-content
description: The filter driver's implementation to detect if a charger is attached and get details about the charger.
old-location: buses\ufx_proprietary_charger_detect.htm
old-project: usbref
ms.assetid: E95D2713-8F95-460E-9107-4793B002A6AC
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ufx_proprietary_charger_detect, UfxProprietaryChargerDetect callback function [Buses], UfxProprietaryChargerDetect, UFX_PROPRIETARY_CHARGER_DETECT, UFX_PROPRIETARY_CHARGER_DETECT, ufxproprietarycharger/UfxProprietaryChargerDetect, PFN_UFX_PROPRIETARY_CHARGER_DETECT callback function pointer [Buses], PFN_UFX_PROPRIETARY_CHARGER_DETECT
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ufxproprietarycharger.h
apiname:
-	PFN_UFX_PROPRIETARY_CHARGER_DETECT
product: Windows
targetos: Windows
req.typenames: "*PUFX_ENDPOINT_CALLBACKS, UFX_ENDPOINT_CALLBACKS"
req.product: Windows 10 or later.
---

# UFX_PROPRIETARY_CHARGER_DETECT callback


## -description


The filter driver's implementation to detect if a charger is attached  and get details about the charger.


## -prototype


````
UFX_PROPRIETARY_CHARGER_DETECT UfxProprietaryChargerDetect;

NTSTATUS UfxProprietaryChargerDetect(
  _In_  PVOID                    Context,
  _Out_ PUFX_PROPRIETARY_CHARGER DetectedCharger
)
{ ... }

typedef UFX_PROPRIETARY_CHARGER_DETECT PFN_UFX_PROPRIETARY_CHARGER_DETECT;
````


## -parameters




#### - Context [in]

    A pointer to a driver-defined context.


#### - DetectedCharger [out]

A pointer to a     <a href="..\ufxproprietarycharger\ns-ufxproprietarycharger-_ufx_proprietary_charger.md">UFX_PROPRIETARY_CHARGER</a> structure that the driver fills with charger information. 


## -returns


If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.



## -remarks


To support handling of proprietary chargers, the USB lower filter driver must publish support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>.

In this callback function, the driver assigns the charger a GUID and sets the minimum required Dx state when the device is connected for charging. 



## -see-also

<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UFX_PROPRIETARY_CHARGER_DETECT callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

