---
UID: NF:wdfdevice.WdfDeviceUnmapIoSpace
title: WdfDeviceUnmapIoSpace function (wdfdevice.h)
description: The WdfDeviceUnmapIoSpace function unmaps a specified range of physical addresses previously mapped by the WdfDeviceMapIoSpace function.
old-location: wdf\wdfdeviceunmapiospace.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDeviceUnmapIoSpace function"]
ms.keywords: WdfDeviceUnmapIoSpace, WdfDeviceUnmapIoSpace function, wdf.wdfdeviceunmapiospace, wdfdevice/WdfDeviceUnmapIoSpace
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceUnmapIoSpace
 - wdfdevice/WdfDeviceUnmapIoSpace
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WUDFx02000.dll
api_name:
 - WdfDeviceUnmapIoSpace
---

# WdfDeviceUnmapIoSpace function


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfDeviceUnmapIoSpace</b> function unmaps a specified range of physical addresses previously mapped by the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicemapiospace">WdfDeviceMapIoSpace</a> function.

## -parameters

### -param Device [in]


A handle to a framework device object.

### -param PseudoBaseAddress [in]


The address of a location that receives a pointer to the pseudo base address.

### -param NumberOfBytes [in]


Specifies a value greater than zero, indicating the number of bytes to be mapped.

## -remarks

This function is the UMDF version 2 equivalent of <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-unmapiospace">IWDFDevice3::UnmapIoSpace</a>.

If a driver calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicemapiospace">WdfDeviceMapIoSpace</a> in <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback, it must call <b>WdfDeviceUnmapIoSpace</b> in its <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-unmapiospace">IWDFDevice3::UnmapIoSpace</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicemapiospace">WdfDeviceMapIoSpace</a>
