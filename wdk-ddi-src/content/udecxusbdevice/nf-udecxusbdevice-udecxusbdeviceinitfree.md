---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitFree
title: UdecxUsbDeviceInitFree function
author: windows-driver-content
description: Releases the resources that were allocated by the UdecxUsbDeviceInitAllocate call.
old-location: buses\udecxusbdeviceinitfree.htm
tech.root: usbref
ms.assetid: BBFB8DAD-C187-4EB9-8EB0-BE28284437E1
ms.date: 5/7/2018
ms.keywords: UdecxUsbDeviceInitFree, UdecxUsbDeviceInitFree function [Buses], buses.udecxusbdeviceinitfree, udecxusbdevice/UdecxUsbDeviceInitFree
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
-	UdecxUsbDeviceInitFree
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceInitFree function


## -description


Releases the resources that were allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt627968">UdecxUsbDeviceInitAllocate</a> call. 


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627968">UdecxUsbDeviceInitAllocate</a>. 


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

