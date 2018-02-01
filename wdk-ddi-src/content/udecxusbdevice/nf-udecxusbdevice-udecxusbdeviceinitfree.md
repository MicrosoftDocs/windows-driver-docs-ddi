---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitFree
title: UdecxUsbDeviceInitFree function
author: windows-driver-content
description: Releases the resources that were allocated by the UdecxUsbDeviceInitAllocate call.
old-location: buses\udecxusbdeviceinitfree.htm
old-project: usbref
ms.assetid: BBFB8DAD-C187-4EB9-8EB0-BE28284437E1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UdecxUsbDeviceInitFree function [Buses], buses.udecxusbdeviceinitfree, udecxusbdevice/UdecxUsbDeviceInitFree, UdecxUsbDeviceInitFree
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
-	UdecxUsbDeviceInitFree
product: Windows
targetos: Windows
req.typenames: "*PUDECX_USB_DEVICE_WAKE_SETTING, UDECX_USB_DEVICE_WAKE_SETTING"
req.product: Windows 10 or later.
---

# UdecxUsbDeviceInitFree function


## -description


Releases the resources that were allocated by the <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a> call. 


## -syntax


````
void UdecxUsbDeviceInitFree(
  _Inout_ PUDECXUSBDEVICE_INIT UdecxUsbDeviceInit
);
````


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>. 


## -returns


This function does not return a value.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceInitFree function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

