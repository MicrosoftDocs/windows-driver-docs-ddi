---
UID: NF:wdfdevice.WdfDeviceGetDeviceStackIoType
title: WdfDeviceGetDeviceStackIoType function (wdfdevice.h)
description: The WdfDeviceGetDeviceStackIoType method retrieves the buffer access methods that the framework is using for a device.
old-location: wdf\wdfdevicegetdevicestackiotype.htm
tech.root: wdf
ms.assetid: E697F53C-2642-4E3F-AA8C-D0802B39D187
ms.date: 02/26/2018
keywords: ["WdfDeviceGetDeviceStackIoType function"]
ms.keywords: WdfDeviceGetDeviceStackIoType, WdfDeviceGetDeviceStackIoType method, wdf.wdfdevicegetdevicestackiotype, wdfdevice/WdfDeviceGetDeviceStackIoType
f1_keywords:
 - "wdfdevice/WdfDeviceGetDeviceStackIoType"
 - "WdfDeviceGetDeviceStackIoType"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- WUDFx02000.dll
api_name:
- WdfDeviceGetDeviceStackIoType
targetos: Windows
req.typenames: 
---

# WdfDeviceGetDeviceStackIoType function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfDeviceGetDeviceStackIoType</b> method retrieves the buffer access methods that the framework is using for a device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param ReadWriteIoType [out]

A pointer to a driver-allocated location that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed value. This value identifies the buffer access method that the framework is using for a device's read and write requests.


### -param IoControlIoType [out]

A pointer to a driver-allocated location that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed value. This value that identifies the buffer access method that the framework is using for a device's I/O control requests.


## -remarks



If your driver calls <b>WdfDeviceGetDeviceStackIoType</b> before the PnP manager has loaded all of the device's drivers, the values that <b>WdfDeviceGetDeviceStackIoType</b> retrieves might not be the values that it actually uses.

For more information about how the framework chooses a buffer access method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-buffer-access-methods-in-umdf-drivers">Managing Buffer Access Methods in UMDF Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>
 

 

