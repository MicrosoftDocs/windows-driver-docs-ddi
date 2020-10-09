---
UID: NF:wdfdevice.WdfDeviceInitSetIoType
title: WdfDeviceInitSetIoType function (wdfdevice.h)
description: The WdfDeviceInitSetIoType method sets the method or preference for how a driver will access the data buffers that are included in read and write requests for a specified device.
old-location: wdf\wdfdeviceinitsetiotype.htm
tech.root: wdf
ms.assetid: fcad4b8e-4273-43ff-8077-a96d1bd4640a
ms.date: 02/26/2018
keywords: ["WdfDeviceInitSetIoType function"]
ms.keywords: DFDeviceObjectGeneralRef_4c821466-f1d7-46fa-a1f0-e8fefd20caab.xml, WdfDeviceInitSetIoType, WdfDeviceInitSetIoType method, kmdf.wdfdeviceinitsetiotype, wdf.wdfdeviceinitsetiotype, wdfdevice/WdfDeviceInitSetIoType
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceInitSetIoType
 - wdfdevice/WdfDeviceInitSetIoType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfDeviceInitSetIoType
---

# WdfDeviceInitSetIoType function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceInitSetIoType</b> method sets the method or preference for how a driver will access the data buffers that are included in read and write requests for a specified device.

## -parameters

### -param DeviceInit 

[in]
A pointer to a <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

### -param IoType 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed enumerator that identifies the method that the driver will use to access data buffers that it receives for read and write requests.

## -remarks

<b>KMDF </b>If you are writing a new driver using KMDF version 1.13 or later, you should instead use <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>. Calling <b>WdfDeviceInitSetIoType</b> from a KMDF filter driver has no effect. For filter drivers, the framework uses the I/O type specified by the next-lower driver in the driver stack.

<b>UMDF </b>If you are converting a KMDF driver that calls <b>WdfDeviceInitSetIoType</b> to UMDF version 2.0 or later, your converted driver can continue to call <b>WdfDeviceInitSetIoType</b> without issue. However, if you are writing an entirely  new driver using UMDF version 2.0 or later, you should instead use <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>.

If a driver calls <b>WdfDeviceInitSetIoType</b>, it must do so before it calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

If the driver does not call <b>WdfDeviceInitSetIoType</b>, the framework sets the driver's buffer-access method to <b>WdfDeviceIoBuffered</b>, for the specified device.

For more information about buffer-access methods, see <a href="/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers</a>.


#### Examples

The following code example indicates that a driver will use the direct I/O method when it accesses the device.

```cpp
WdfDeviceInitSetIoType(
                       DeviceInit,
                       WdfDeviceIoDirect
                       );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdeviceinitialize2-setiotypepreference"> IWDFDeviceInitialize2::SetIoTypePreference</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>