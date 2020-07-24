---
UID: NF:udecxusbdevice.UdecxUsbDeviceSetFunctionSuspendAndWakeComplete
title: UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function (udecxusbdevice.h)
description: Completes an asynchronous request for changing the power state of a particular function of a virtual USB 3.0 device.
old-location: buses\udecxusbdevicesetfunctionsuspendandwakecomplete.htm
tech.root: usbref
ms.assetid: 21339CB5-8529-4649-9F1A-9D8C80709407
ms.date: 05/07/2018
keywords: ["UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function"]
ms.keywords: UdecxUsbDeviceSetFunctionSuspendAndWakeComplete, UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function [Buses], buses.udecxusbdevicesetfunctionsuspendandwakecomplete, udecxusbdevice/UdecxUsbDeviceSetFunctionSuspendAndWakeComplete
f1_keywords:
 - "udecxusbdevice/UdecxUsbDeviceSetFunctionSuspendAndWakeComplete"
 - "UdecxUsbDeviceSetFunctionSuspendAndWakeComplete"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxUsbDeviceSetFunctionSuspendAndWakeComplete
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function


## -description


Completes an asynchronous request for changing the power state of a particular function of a virtual USB 3.0 device. 


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.


### -param CompletionStatus [in]

An appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code that indicates the success or failure of the asynchronous operation.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_set_function_suspend_and_wake">EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

