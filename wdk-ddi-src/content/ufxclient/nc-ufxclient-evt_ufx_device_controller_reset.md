---
UID: NC:ufxclient.EVT_UFX_DEVICE_CONTROLLER_RESET
title: EVT_UFX_DEVICE_CONTROLLER_RESET
author: windows-driver-content
description: The client driver's implementation to reset the function controller to its initial state.
old-location: buses\evt_ufx_device_controller_reset.htm
tech.root: usbref
ms.assetid: 37CE6358-68F8-49E2-8B3E-126D5D135ADF
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: EVT_UFX_DEVICE_CONTROLLER_RESET, EVT_UFX_DEVICE_CONTROLLER_RESET callback, EvtUfxDeviceControllerReset, EvtUfxDeviceControllerReset callback function [Buses], PFN_UFX_DEVICE_CONTROLLER_RESET, PFN_UFX_DEVICE_CONTROLLER_RESET callback function pointer [Buses], buses.evt_ufx_device_controller_reset, ufxclient/EvtUfxDeviceControllerReset
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
-	PFN_UFX_DEVICE_CONTROLLER_RESET
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_CONTROLLER_RESET callback function


## -description


The client driver's implementation to reset the function controller to its initial state.


## -parameters












#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


#### - UfxHardwareFailureContext [in, optional]

A pointer to a variable-length UFX_HARDWARE_FAILURE_CONTEXT structure allocated by the client driver.


## -returns



This callback function does not return a value.




## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_CONTROLLER_RESET</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.

The client driver indicates completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a> method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a>
 

 

