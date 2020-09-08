---
UID: NC:udecxwdfdevice.EVT_UDECX_WDF_DEVICE_RESET
title: EVT_UDECX_WDF_DEVICE_RESET (udecxwdfdevice.h)
description: The UDE client driver's implementation to reset the emulated host controller or the devices attached to it.
old-location: buses\evt_udecx_wdf_device_reset.htm
tech.root: usbref
ms.assetid: 394343A5-10E4-4F64-AD3C-1D2114422B39
ms.date: 05/07/2018
keywords: ["EVT_UDECX_WDF_DEVICE_RESET callback function"]
ms.keywords: EVT_UDECX_WDF_DEVICE_RESET, EVT_UDECX_WDF_DEVICE_RESET callback, EvtUdecxWdfDeviceReset, EvtUdecxWdfDeviceReset callback function [Buses], buses.evt_udecx_wdf_device_reset, udecxwdfdevice/EvtUdecxWdfDeviceReset
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
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UDECX_WDF_DEVICE_RESET
 - udecxwdfdevice/EVT_UDECX_WDF_DEVICE_RESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - UdecxWdfDevice.h
api_name:
 - EvtUdecxWdfDeviceReset
---

# EVT_UDECX_WDF_DEVICE_RESET callback function


## -description

The UDE client driver's implementation to reset the emulated host controller or the devices attached to it.

## -parameters

### -param UdecxWdfDevice 

[in]
A handle to a framework device object that represents the controller. The client driver initialized this object in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>.

## -remarks

The USB device emulation  class extension (UdeCx) invokes this callback function to notify the client driver that it must handle a reset request including resetting all downstream devices attached to the emulated host controller.
This call is asynchronous. The client driver signals completion with status information by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceresetcomplete">UdecxWdfDeviceResetComplete</a>.
If the client specified <b>UdeWdfDeviceResetActionResetEachUsbDevice</b> in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxwdfdevice/ns-udecxwdfdevice-_udecx_wdf_device_config">UDECX_WDF_DEVICE_CONFIG</a> (during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a> call), this callback is never used. Instead, each connected attached device receives an <i>EVT_UDECX_WDF_DEVICE_RESET</i> callback.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>

