---
UID: NF:udecxusbdevice.UdecxUsbDeviceSetFunctionSuspendAndWakeComplete
title: UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function
author: windows-driver-content
description: Completes an asynchronous request for changing the power state of a particular function of a virtual USB 3.0 device.
old-location: buses\udecxusbdevicesetfunctionsuspendandwakecomplete.htm
tech.root: usbref
ms.assetid: 21339CB5-8529-4649-9F1A-9D8C80709407
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UdecxUsbDeviceSetFunctionSuspendAndWakeComplete, UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function [Buses], buses.udecxusbdevicesetfunctionsuspendandwakecomplete, udecxusbdevice/UdecxUsbDeviceSetFunctionSuspendAndWakeComplete
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	UdecxUsbDeviceSetFunctionSuspendAndWakeComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function


## -description


Completes an asynchronous request for changing the power state of a particular function of a virtual USB 3.0 device. 


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.


### -param CompletionStatus [in]

An appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code that indicates the success or failure of the asynchronous operation.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595915">EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

