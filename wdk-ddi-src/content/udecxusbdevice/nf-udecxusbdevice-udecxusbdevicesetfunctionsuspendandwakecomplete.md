---
UID: NF:udecxusbdevice.UdecxUsbDeviceSetFunctionSuspendAndWakeComplete
title: UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function
author: windows-driver-content
description: Completes an asynchronous request for changing the power state of a particular function of a virtual USB 3.0 device.
old-location: buses\udecxusbdevicesetfunctionsuspendandwakecomplete.htm
old-project: usbref
ms.assetid: 21339CB5-8529-4649-9F1A-9D8C80709407
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.udecxusbdevicesetfunctionsuspendandwakecomplete, UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function [Buses], UdecxUsbDeviceSetFunctionSuspendAndWakeComplete, udecxusbdevice/UdecxUsbDeviceSetFunctionSuspendAndWakeComplete
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Udecxstub.lib
-	Udecxstub.dll
apiname:
-	UdecxUsbDeviceSetFunctionSuspendAndWakeComplete
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function


## -description


Completes an asynchronous request for changing the power state of a particular function of a virtual USB 3.0 device. 


## -syntax


````
void UdecxUsbDeviceSetFunctionSuspendAndWakeComplete(
  _In_ UDECXUSBDEVICE UdecxUsbDevice,
  _In_ NTSTATUS       CompletionStatus
);
````


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.


### -param CompletionStatus [in]

An appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code that indicates the success or failure of the asynchronous operation.


## -returns



This function does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_set_function_suspend_and_wake.md">EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

