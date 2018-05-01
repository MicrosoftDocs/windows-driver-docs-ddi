---
UID: NF:wdfdevice.WdfDeviceUnmapIoSpace
title: WdfDeviceUnmapIoSpace function
author: windows-driver-content
description: The WdfDeviceUnmapIoSpace function unmaps a specified range of physical addresses previously mapped by the WdfDeviceMapIoSpace function.
old-location: wdf\wdfdeviceunmapiospace.htm
old-project: wdf
ms.assetid: C8963667-D2FB-4360-A523-33429D6FBF1B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDeviceUnmapIoSpace, WdfDeviceUnmapIoSpace function, wdf.wdfdeviceunmapiospace, wdfdevice/WdfDeviceUnmapIoSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfDeviceUnmapIoSpace
product: Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceUnmapIoSpace function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfDeviceUnmapIoSpace</b> function unmaps a specified range of physical addresses previously mapped by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265605">WdfDeviceMapIoSpace</a> function.


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



This function is the UMDF version 2 equivalent of <a href="https://msdn.microsoft.com/E95AC8E6-222A-4C88-8EBD-6BD7F22B9F18">IWDFDevice3::UnmapIoSpace</a>.

If a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/dn265605">WdfDeviceMapIoSpace</a> in <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback, it must call <b>WdfDeviceUnmapIoSpace</b> in its <a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a> callback.






## -see-also




<a href="https://msdn.microsoft.com/E95AC8E6-222A-4C88-8EBD-6BD7F22B9F18">IWDFDevice3::UnmapIoSpace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265605">WdfDeviceMapIoSpace</a>
 

 

