---
UID: NC:ufxclient.EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
title: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET (ufxclient.h)
description: The client driver's implementation to resets proprietary charger.
old-location: buses\evt_ufx_device_proprietary_charger_reset.htm
tech.root: usbref
ms.assetid: 103E60D4-4640-430D-A4AE-E03D8B6E7031
ms.date: 05/07/2018
ms.keywords: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET, EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback, EvtUfxDeviceProprietaryChargerReset, EvtUfxDeviceProprietaryChargerReset callback function [Buses], PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET, PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback function pointer [Buses], buses.evt_ufx_device_proprietary_charger_reset, ufxclient/EvtUfxDeviceProprietaryChargerReset
ms.topic: callback
req.header: ufxclient.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ufxclient.h
api_name:
-	PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback function


## -description


The client driver's implementation to resets proprietary charger. 


## -parameters




### -param Arg1








#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



<i>EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET</i> is an optional event callback.

The USB function class extension (UFX) invokes this  event callback to indicate that the USB device has been detached from the charger.  The client driver initiates a request to the lower filter driver to reset the proprietary charger its initial state.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187964">UfxDeviceProprietaryChargerDetectComplete</a>
 

 

