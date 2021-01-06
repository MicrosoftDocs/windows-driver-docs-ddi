---
UID: NF:wdfdevice.WdfDeviceClearRemovalRelationsDevices
title: WdfDeviceClearRemovalRelationsDevices function (wdfdevice.h)
description: The WdfDeviceClearRemovalRelationsDevices method removes all devices from the list of devices that must be removed when a specified device is removed.
old-location: wdf\wdfdeviceclearremovalrelationsdevices.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDeviceClearRemovalRelationsDevices function"]
ms.keywords: DFDeviceObjectGeneralRef_e2dc5cb6-4f45-441c-b242-5b67ea8fa381.xml, WdfDeviceClearRemovalRelationsDevices, WdfDeviceClearRemovalRelationsDevices method, kmdf.wdfdeviceclearremovalrelationsdevices, wdf.wdfdeviceclearremovalrelationsdevices, wdfdevice/WdfDeviceClearRemovalRelationsDevices
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
 - WdfDeviceClearRemovalRelationsDevices
 - wdfdevice/WdfDeviceClearRemovalRelationsDevices
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceClearRemovalRelationsDevices
---

# WdfDeviceClearRemovalRelationsDevices function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceClearRemovalRelationsDevices</b> method removes all devices from the list of devices that must be removed when a specified device is removed.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceaddremovalrelationsphysicaldevice">WdfDeviceAddRemovalRelationsPhysicalDevice</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceremoveremovalrelationsphysicaldevice">WdfDeviceRemoveRemovalRelationsPhysicalDevice</a>
