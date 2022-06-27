---
UID: NF:wdfdevice.WdfDeviceGetDeviceState
title: WdfDeviceGetDeviceState function (wdfdevice.h)
description: The WdfDeviceGetDeviceState method retrieves the device state for a specified device.
old-location: wdf\wdfdevicegetdevicestate.htm
tech.root: wdf
ms.date: 01/26/2022
keywords: ["WdfDeviceGetDeviceState function"]
ms.keywords: DFDeviceObjectGeneralRef_459b9aad-7503-4319-be67-4b713a32559e.xml, WdfDeviceGetDeviceState, WdfDeviceGetDeviceState method, kmdf.wdfdevicegetdevicestate, wdf.wdfdevicegetdevicestate, wdfdevice/WdfDeviceGetDeviceState
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
 - WdfDeviceGetDeviceState
 - wdfdevice/WdfDeviceGetDeviceState
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
 - WdfDeviceGetDeviceState
---

# WdfDeviceGetDeviceState function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceGetDeviceState</b> method retrieves the device state for a specified device.

## -parameters

### -param Device [in]


A handle to a framework device object.

### -param DeviceState [in, out]


A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_state">WDF_DEVICE_STATE</a> structure that receives the device's state information.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_device_state_init">WDF_DEVICE_STATE_INIT</a>
