---
UID: NC:udecxwdfdevice.EVT_UDECX_WDF_DEVICE_RESET
title: EVT_UDECX_WDF_DEVICE_RESET
description: The UDE client driver's implementation to reset the emulated host controller or the devices attached to it.
old-location: buses\evt_udecx_wdf_device_reset.htm
tech.root: usbref
ms.assetid: 394343A5-10E4-4F64-AD3C-1D2114422B39
ms.date: 05/07/2018
ms.keywords: EVT_UDECX_WDF_DEVICE_RESET, EVT_UDECX_WDF_DEVICE_RESET callback, EvtUdecxWdfDeviceReset, EvtUdecxWdfDeviceReset callback function [Buses], buses.evt_udecx_wdf_device_reset, udecxwdfdevice/EvtUdecxWdfDeviceReset
ms.topic: callback
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	UdecxWdfDevice.h
api_name:
-	EvtUdecxWdfDeviceReset
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UDECX_WDF_DEVICE_RESET callback function


## -description


The UDE client driver's implementation to reset the emulated host controller or the devices attached to it.


## -parameters




### -param UdecxWdfDevice [in]

A handle to a framework device object that represents the controller. The client driver initialized this object in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627990">UdecxWdfDeviceAddUsbDeviceEmulation</a>.


## -returns



This callback function does not return a value.




## -remarks



The USB device emulation  class extension (UdeCx) invokes this callback function to notify the client driver that it must handle a reset request including resetting all downstream devices attached to the emulated host controller.
This call is asynchronous. The client driver signals completion with status information by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt627991">UdecxWdfDeviceResetComplete</a>.
If the client specified <b>UdeWdfDeviceResetActionResetEachUsbDevice</b> in <a href="https://msdn.microsoft.com/library/windows/hardware/mt628008">UDECX_WDF_DEVICE_CONFIG</a> (during the <a href="https://msdn.microsoft.com/library/windows/hardware/mt627990">UdecxWdfDeviceAddUsbDeviceEmulation</a> call), this callback is never used. Instead, each connected attached device receives an <i>EVT_UDECX_WDF_DEVICE_RESET</i> callback.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

