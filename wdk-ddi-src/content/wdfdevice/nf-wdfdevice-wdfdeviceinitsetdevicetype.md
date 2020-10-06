---
UID: NF:wdfdevice.WdfDeviceInitSetDeviceType
title: WdfDeviceInitSetDeviceType function (wdfdevice.h)
description: The WdfDeviceInitSetDeviceType method sets the device type for a specified device.
old-location: wdf\wdfdeviceinitsetdevicetype.htm
tech.root: wdf
ms.assetid: 26c5c998-fb10-45c3-b28c-91a759fa941e
ms.date: 02/26/2018
keywords: ["WdfDeviceInitSetDeviceType function"]
ms.keywords: DFDeviceObjectGeneralRef_872eb4dd-0d40-46ed-a7ed-4eae8ec67240.xml, WdfDeviceInitSetDeviceType, WdfDeviceInitSetDeviceType method, kmdf.wdfdeviceinitsetdevicetype, wdf.wdfdeviceinitsetdevicetype, wdfdevice/WdfDeviceInitSetDeviceType
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceInitSetDeviceType
 - wdfdevice/WdfDeviceInitSetDeviceType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceInitSetDeviceType
---

# WdfDeviceInitSetDeviceType function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitSetDeviceType</b> method sets the device type for a specified device.

## -parameters

### -param DeviceInit 

[in]
A pointer to a <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

### -param DeviceType 

[in]
A FILE_DEVICE_XXXX value that identifies the device type. For more information about FILE_DEVICE_XXXX values, see <a href="/windows-hardware/drivers/kernel/specifying-device-types">Specifying Device Types</a>.

## -remarks

If a driver calls <b>WdfDeviceInitSetDeviceType</b>, it must do so before it calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

For more information about calling <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>, see <a href="/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

The device type that a driver specifies determines the default priority boost value that the framework uses when the driver completes an I/O request. For more information about priority boost values, see <a href="/windows-hardware/drivers/wdf/specifying-priority-boosts-when-completing-i-o-requests">Specifying Priority Boosts When Completing I/O Requests</a>.


If you are writing a UMDF driver, you  must modify your driver's INF file or make registry changes to specify a device type. For more information about using the registry, see <a href="/windows-hardware/drivers/kernel/setting-device-object-registry-properties-during-installation">Setting Device Object Registry Properties During Installation</a>.


#### Examples

The following code example indicates that a device is a serial device.

```cpp
WdfDeviceInitSetDeviceType(
                           DeviceInit,
                           FILE_DEVICE_SERIAL_PORT
                           );
```