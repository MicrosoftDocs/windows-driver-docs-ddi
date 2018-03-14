---
UID: NC:ufxclient.EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
title: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
author: windows-driver-content
description: The client driver's implementation to resets proprietary charger.
old-location: buses\evt_ufx_device_proprietary_charger_reset.htm
old-project: usbref
ms.assetid: 103E60D4-4640-430D-A4AE-E03D8B6E7031
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET, EvtUfxDeviceProprietaryChargerReset, EvtUfxDeviceProprietaryChargerReset callback function [Buses], PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET, PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback function pointer [Buses], buses.evt_ufx_device_proprietary_charger_reset, ufxclient/EvtUfxDeviceProprietaryChargerReset
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback


## -description


The client driver's implementation to resets proprietary charger. 


## -prototype


````
EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET EvtUfxDeviceProprietaryChargerReset;

void EvtUfxDeviceProprietaryChargerReset(
  _In_ UFXDEVICE UfxDevice
)
{ ... }

typedef EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET;
````


## -parameters










#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



<i>EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET</i> is an optional event callback.

The USB function class extension (UFX) invokes this  event callback to indicate that the USB device has been detached from the charger.  The client driver initiates a request to the lower filter driver to reset the proprietary charger its initial state.




## -see-also

<a href="..\ufxclient\nf-ufxclient-ufxdeviceproprietarychargerdetectcomplete.md">UfxDeviceProprietaryChargerDetectComplete</a>



<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>



 

 


