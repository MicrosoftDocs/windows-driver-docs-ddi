---
UID: NF:udecxwdfdevice.UdecxWdfDeviceResetComplete
title: UdecxWdfDeviceResetComplete function (udecxwdfdevice.h)
description: Informs the USB device emulation class extension (UdeCx) that the reset operation on the specified controller has competed.
old-location: buses\udecxwdfdeviceresetcomplete.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxWdfDeviceResetComplete function"]
ms.keywords: UdecxWdfDeviceResetComplete, UdecxWdfDeviceResetComplete function [Buses], buses.udecxwdfdeviceresetcomplete, udecxwdfdevice/UdecxWdfDeviceResetComplete
req.header: udecxwdfdevice.h
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UdecxWdfDeviceResetComplete
 - udecxwdfdevice/UdecxWdfDeviceResetComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxWdfDeviceResetComplete
---

# UdecxWdfDeviceResetComplete function


## -description

Informs the  USB device emulation  class extension (UdeCx) that the reset operation on the specified controller has competed.

## -parameters

### -param UdeWdfDevice

<p>A handle to a framework device object that represents the controller that has been reset. The client driver initialized this object in the previous call to <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation"><b>UdecxWdfDeviceAddUsbDeviceEmulation</b></a>.</p>

## -remarks

When the class extension calls the  <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nc-udecxwdfdevice-evt_udecx_wdf_device_reset">EVT_UDECX_WDF_DEVICE_RESET</a> callback function, that call is asynchronous. The client driver must call  <b>UdecxWdfDeviceResetComplete</b> to notify the class extension when the reset operation is complete with appropriate status information.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nc-udecxwdfdevice-evt_udecx_wdf_device_reset">EVT_UDECX_WDF_DEVICE_RESET</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
