---
UID: NC:ufxclient.EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
title: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
author: windows-driver-content
description: The client driver's implementation to initiate proprietary charger detection.
old-location: buses\evt_ufx_device_detect_proprietary_charger.htm
old-project: usbref
ms.assetid: A3396CC8-153E-401A-BAD6-18FEE4D14EE5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER, EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT, EvtDeviceProprietaryChargerDetect, EvtUfxDeviceDetectProprietaryCharger, EvtUfxDeviceDetectProprietaryCharger callback function [Buses], PFN_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT, PFN_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback function pointer [Buses], buses.evt_ufx_device_detect_proprietary_charger, ufxclient/EvtUfxDeviceDetectProprietaryCharger
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
-	PFN_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback


## -description


The client driver's implementation to initiate proprietary charger detection.


## -parameters




### -param Arg1








#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



<i>EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</i> is an optional event callback. The client driver is required to implement this event callback only if it supports proprietary charger detection. The driver indicates its support in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> call by setting <b>PdcpSupported</b> to TRUE in <a href="https://msdn.microsoft.com/library/windows/hardware/mt187973">UFX_DEVICE_CAPABILITIES</a>. If the client driver does not support the functionality, the <b>EvtDeviceProprietaryChargerDetect</b>, <b>EvtDeviceProprietaryChargerSetProperty</b>, and <b>EvtDeviceProprietaryChargerReset</b>
members of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187971">UFX_DEVICE_CALLBACKS</a> structure must be set to NULL in   <b>UfxDeviceCreate</b>.   

The client driver indicates completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187964">UfxDeviceProprietaryChargerDetectComplete</a> method.

The client driver sends a request to the lower filter driver to determine if a proprietary charger is present. In response, the filter driver provides a GUID for each charger type it supports, and a list of that charger’s properties.  If a specific charger is configurable, the filter driver also provides a list of supported PropertyIDs and their possible values to configure the charger.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187964">UfxDeviceProprietaryChargerDetectComplete</a>
 

 

