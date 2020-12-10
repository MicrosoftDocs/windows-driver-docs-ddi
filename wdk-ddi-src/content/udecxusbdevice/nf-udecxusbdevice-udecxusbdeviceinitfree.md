---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitFree
title: UdecxUsbDeviceInitFree function (udecxusbdevice.h)
description: Releases the resources that were allocated by the UdecxUsbDeviceInitAllocate call.
old-location: buses\udecxusbdeviceinitfree.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUsbDeviceInitFree function"]
ms.keywords: UdecxUsbDeviceInitFree, UdecxUsbDeviceInitFree function [Buses], buses.udecxusbdeviceinitfree, udecxusbdevice/UdecxUsbDeviceInitFree
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UdecxUsbDeviceInitFree
 - udecxusbdevice/UdecxUsbDeviceInitFree
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbDeviceInitFree
---

# UdecxUsbDeviceInitFree function


## -description

Releases the resources that were allocated by the <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a> call.

## -parameters

### -param UdecxUsbDeviceInit 

[in, out]
A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
