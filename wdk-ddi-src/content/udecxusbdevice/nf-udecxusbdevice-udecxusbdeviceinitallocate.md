---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitAllocate
title: UdecxUsbDeviceInitAllocate function (udecxusbdevice.h)
description: Allocates memory for a UDECXUSBDEVICE_INIT structure that is used to initialize a virtual USB device.
old-location: buses\udecxusbdeviceinitallocate.htm
tech.root: usbref
ms.assetid: 127D132B-6A40-4F6F-BCDA-473F89A1A747
ms.date: 05/07/2018
keywords: ["UdecxUsbDeviceInitAllocate function"]
ms.keywords: UdecxUsbDeviceInitAllocate, UdecxUsbDeviceInitAllocate function [Buses], buses.udecxusbdeviceinitallocate, udecxusbdevice/UdecxUsbDeviceInitAllocate
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
 - UdecxUsbDeviceInitAllocate
 - udecxusbdevice/UdecxUsbDeviceInitAllocate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbDeviceInitAllocate
---

# UdecxUsbDeviceInitAllocate function


## -description

Allocates memory for a  <b>UDECXUSBDEVICE_INIT</b> structure that is used to initialize a virtual USB device.

## -parameters

### -param UdecxWdfDevice 

[in]
A handle to a framework device object that represents the a USB device. The client driver initialized this object in the previous call to <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>.

## -returns

This method returns a pointer to an opaque <b>UDECXUSBDEVICE_INIT</b> that contains the initialization parameters. The structure is allocated by the USB device emulation  class extension (UdeCx).

## -remarks

The UDE client driver calls this method to allocate parameters for the virtual device that is created by a subsequent call to <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicecreate">UdecxUsbDeviceCreate</a>. If the device is not created or the driver is finished using the resources, the driver must free the resources by calling <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitfree">UdecxUsbDeviceInitFree</a>.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>