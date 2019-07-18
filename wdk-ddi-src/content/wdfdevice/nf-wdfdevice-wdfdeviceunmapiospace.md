---
UID: NF:wdfdevice.WdfDeviceUnmapIoSpace
title: WdfDeviceUnmapIoSpace function (wdfdevice.h)
description: The WdfDeviceUnmapIoSpace function unmaps a specified range of physical addresses previously mapped by the WdfDeviceMapIoSpace function.
old-location: wdf\wdfdeviceunmapiospace.htm
tech.root: wdf
ms.assetid: C8963667-D2FB-4360-A523-33429D6FBF1B
ms.date: 02/26/2018
ms.keywords: WdfDeviceUnmapIoSpace, WdfDeviceUnmapIoSpace function, wdf.wdfdeviceunmapiospace, wdfdevice/WdfDeviceUnmapIoSpace
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceUnmapIoSpace"
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
- WdfDeviceUnmapIoSpace
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceUnmapIoSpace function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfDeviceUnmapIoSpace</b> function unmaps a specified range of physical addresses previously mapped by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicemapiospace">WdfDeviceMapIoSpace</a> function.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PseudoBaseAddress [in]

The address of a location that receives a pointer to the pseudo base address.




### -param NumberOfBytes [in]

Specifies a value greater than zero, indicating the number of bytes to be mapped.


## -returns



This function does not return a value.




## -remarks



This function is the UMDF version 2 equivalent of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice3-unmapiospace">IWDFDevice3::UnmapIoSpace</a>.

If a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicemapiospace">WdfDeviceMapIoSpace</a> in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback, it must call <b>WdfDeviceUnmapIoSpace</b> in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback.






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice3-unmapiospace">IWDFDevice3::UnmapIoSpace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicemapiospace">WdfDeviceMapIoSpace</a>
 

 

