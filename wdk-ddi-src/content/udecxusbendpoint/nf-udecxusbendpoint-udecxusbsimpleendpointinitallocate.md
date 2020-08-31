---
UID: NF:udecxusbendpoint.UdecxUsbSimpleEndpointInitAllocate
title: UdecxUsbSimpleEndpointInitAllocate function (udecxusbendpoint.h)
description: Allocates memory for an initialization structure that is used to create a simple endpoint for the specified virtual USB device.
old-location: buses\udecxusbsimpleendpointinitallocate.htm
tech.root: usbref
ms.assetid: 1BF79756-F55D-4F13-A03C-35F7880C5B21
ms.date: 05/07/2018
keywords: ["UdecxUsbSimpleEndpointInitAllocate function"]
ms.keywords: UdecxUsbSimpleEndpointInitAllocate, UdecxUsbSimpleEndpointInitAllocate function [Buses], buses.udecxusbsimpleendpointinitallocate, udecxusbendpoint/UdecxUsbSimpleEndpointInitAllocate
req.header: udecxusbendpoint.h
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
 - UdecxUsbSimpleEndpointInitAllocate
 - udecxusbendpoint/UdecxUsbSimpleEndpointInitAllocate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbSimpleEndpointInitAllocate
---

# UdecxUsbSimpleEndpointInitAllocate function


## -description

Allocates memory for an initialization  structure that is used to create a simple endpoint for the specified virtual USB device.

## -parameters

### -param UdecxUsbDevice 

[in]
A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.

## -returns

This method returns a pointer to an opaque <b>UDECXUSBENDPOINT_INIT</b> structure that contains the initialization parameters. The structure is allocated by the USB device emulation  class extension (UdeCx).

## -remarks

The UDE client driver calls this method to allocate parameters for a simple endpoint that is created by a subsequent call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>. If the device is not created or the driver is finished using the resources, the driver must free the resources by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointinitfree">UdecxUsbEndpointInitFree</a>.

The only valid time to create simple endpoints is after creating a the UDE device object and before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceplugin">UdecxUsbDevicePlugIn</a> on the device.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>

