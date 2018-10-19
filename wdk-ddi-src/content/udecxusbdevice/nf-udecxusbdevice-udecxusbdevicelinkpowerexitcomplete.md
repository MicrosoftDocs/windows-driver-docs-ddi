---
UID: NF:udecxusbdevice.UdecxUsbDeviceLinkPowerExitComplete
title: UdecxUsbDeviceLinkPowerExitComplete function
author: windows-driver-content
description: Completes an asynchronous request for sending the device to a low power state.
old-location: buses\udecxusbdevicelinkpowerexitcomplete.htm
tech.root: usbref
ms.assetid: EB41B75C-57E0-4E09-8A7A-2D6BB377ACE7
ms.date: 05/07/2018
ms.keywords: UdecxUsbDeviceLinkPowerExitComplete, UdecxUsbDeviceLinkPowerExitComplete function [Buses], buses.udecxusbdevicelinkpowerexitcomplete, udecxusbdevice/UdecxUsbDeviceLinkPowerExitComplete
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
-	UdecxUsbDeviceLinkPowerExitComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceLinkPowerExitComplete function


## -description


Completes an asynchronous request for sending the device to a low power state.  


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.


### -param CompletionStatus [in]

An appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code that indicates the success or failure of the asynchronous operation.


## -returns



This function does not return a value.




## -remarks



When the USB device emulation class extension (UdeCx) gets a request to send the device to a low power state, it invokes the client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt595911">EVT_UDECX_USB_DEVICE_D0_EXIT</a> callback function. 

After the client driver has performed the necessary steps for sending the virtual USB device to low power state, the driver calls this method to notify the class extension that it has completed the power request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595911">EVT_UDECX_USB_DEVICE_D0_EXIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

