---
UID: NF:udecxusbdevice.UdecxUsbDeviceSignalFunctionWake
title: UdecxUsbDeviceSignalFunctionWake function
description: Initiates wake up of the specified function from a low power state. This applies to virtual USB 3.0 devices.
old-location: buses\udecxusbdevicesignalfunctionwake.htm
tech.root: usbref
ms.assetid: 82B3B3BD-CEAC-427E-A89E-84CBE85BDBE7
ms.date: 05/07/2018
ms.keywords: UdecxUsbDeviceSignalFunctionWake, UdecxUsbDeviceSignalFunctionWake function [Buses], buses.udecxusbdevicesignalfunctionwake, udecxusbdevice/UdecxUsbDeviceSignalFunctionWake
ms.topic: function
req.header: udecxusbdevice.h
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
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUsbDeviceSignalFunctionWake
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceSignalFunctionWake function


## -description


Initiates wake up of the specified function from a low power state. This applies to virtual USB 3.0 devices.


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.


### -param Interface [in]

This value is the <b>bInterfaceNumber</b> of the interface that is waking up. 


## -returns



This function does not return a value.




## -remarks



The client driver for the device must have enabled wake capability in the most recent <a href="https://msdn.microsoft.com/library/windows/hardware/mt595915">EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE</a> call.


If the device is in a low power state, or going to such a state, this call also wakes up  the entire device.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595915">EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

