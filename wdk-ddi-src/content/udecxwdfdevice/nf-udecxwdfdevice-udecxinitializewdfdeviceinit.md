---
UID: NF:udecxwdfdevice.UdecxInitializeWdfDeviceInit
title: UdecxInitializeWdfDeviceInit function (udecxwdfdevice.h)
description: UdecxInitializeWdfDeviceInit initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\udecxinitializewdfdeviceinit.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxInitializeWdfDeviceInit function"]
ms.keywords: UdecxInitializeWdfDeviceInit, UdecxInitializeWdfDeviceInit function [Buses], buses.udecxinitializewdfdeviceinit, udecxwdfdevice/UdecxInitializeWdfDeviceInit
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UdecxInitializeWdfDeviceInit
 - udecxwdfdevice/UdecxInitializeWdfDeviceInit
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxInitializeWdfDeviceInit
---

# UdecxInitializeWdfDeviceInit function


## -description

Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

## -parameters

### -param WdfDeviceInit

<p>A pointer to a framework-allocated <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure. </p>

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -remarks

The client driver for the emulated host controller device calls this method in its <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> implementation before it calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> and <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>. For code example, see <b>UdecxWdfDeviceAddUsbDeviceEmulation</b>.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
