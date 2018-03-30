---
UID: NS:d3dumddi.D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
title: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
author: windows-driver-content
description: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU is used with pfnSignalSynchronizationObjectFromGpuCb to signal a monitored fence.
old-location: display\d3dddicb_signalsynchronizationobjectfromgpu.htm
old-project: display
ms.assetid: FF098E63-842F-4D88-A184-BE886E0ED507
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure [Display Devices], d3dumddi/D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU, display.d3dddicb_signalsynchronizationobjectfromgpu
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
product: Windows
targetos: Windows
req.typenames: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
---

# D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure


## -description


<b>D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU</b> is used with <a href="https://msdn.microsoft.com/46F23D7A-5C7A-4BCC-A575-5D47F590B07C">pfnSignalSynchronizationObjectFromGpuCb</a> to signal a monitored fence.


## -struct-fields




### -field hContext

[in] A kernel-mode handle to the context stream.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the <b>hContext</b> member signals.


#### - MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to signal, each of which correspond to a synchronization object in <b>ObjectHandleArray</b>.


#### - Reserved

This member is reserved and should be set to zero.



## -see-also




<a href="https://msdn.microsoft.com/46F23D7A-5C7A-4BCC-A575-5D47F590B07C">pfnSignalSynchronizationObjectFromGpuCb</a>
 

 

