---
UID: NC:ufxclient.EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
title: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
author: windows-driver-content
description: The client driver's implementation to resets proprietary charger.
old-location: buses\evt_ufx_device_proprietary_charger_reset.htm
old-project: usbref
ms.assetid: 103E60D4-4640-430D-A4AE-E03D8B6E7031
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ufx_device_proprietary_charger_reset, EvtUfxDeviceProprietaryChargerReset callback function [Buses], EvtUfxDeviceProprietaryChargerReset, EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET, EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET, ufxclient/EvtUfxDeviceProprietaryChargerReset, PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback function pointer [Buses], PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ufxclient.h
apiname:
-	PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET
product: Windows
targetos: Windows
req.typenames: "*PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT"
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

