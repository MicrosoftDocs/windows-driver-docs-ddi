---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitSetStateChangeCallbacks
title: UdecxUsbDeviceInitSetStateChangeCallbacks function
author: windows-driver-content
description: Initializes a WDF-allocated structure with pointers to callback functions.
old-location: buses\udecxusbdeviceinitsetstatechangecallbacks.htm
tech.root: usbref
ms.assetid: A4D0B6BC-56FD-4378-A8F9-0A306D3FF22F
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UdecxUsbDeviceInitSetStateChangeCallbacks, UdecxUsbDeviceInitSetStateChangeCallbacks function [Buses], buses.udecxusbdeviceinitsetstatechangecallbacks, udecxusbdevice/UdecxUsbDeviceInitSetStateChangeCallbacks
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
-	UdecxUsbDeviceInitSetStateChangeCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceInitSetStateChangeCallbacks function


## -description


Initializes a WDF-allocated structure with pointers to callback functions.


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627968">UdecxUsbDeviceInitAllocate</a>. 


### -param Callbacks [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt628003">UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS</a> structure that contains pointers to callback functions implemented by the client driver.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627968">UdecxUsbDeviceInitAllocate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

