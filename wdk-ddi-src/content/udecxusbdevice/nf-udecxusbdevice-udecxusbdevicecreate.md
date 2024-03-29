---
UID: NF:udecxusbdevice.UdecxUsbDeviceCreate
title: UdecxUsbDeviceCreate function (udecxusbdevice.h)
description: Creates a USB Device Emulation (UDE) device object.
old-location: buses\udecxusbdevicecreate.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUsbDeviceCreate function"]
ms.keywords: UdecxUsbDeviceCreate, UdecxUsbDeviceCreate function [Buses], buses.udecxusbdevicecreate, udecxusbdevice/UdecxUsbDeviceCreate
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
 - UdecxUsbDeviceCreate
 - udecxusbdevice/UdecxUsbDeviceCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbDeviceCreate
---

# UdecxUsbDeviceCreate function


## -description

Creates a USB Device Emulation (UDE) device object.

## -parameters

### -param UdecxUsbDeviceInit [in, out]


A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>.

### -param Attributes [in, optional]


A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the USB device object.

### -param UdecxUsbDevice [out]


A pointer to a variable that receives a handle to the new UDE device object that represents the virtual USB device.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
