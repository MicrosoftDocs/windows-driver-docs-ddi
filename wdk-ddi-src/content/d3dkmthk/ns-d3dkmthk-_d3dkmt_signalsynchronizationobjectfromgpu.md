---
UID: NS:d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
title: _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU (d3dkmthk.h)
description: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU is used with D3DKMTSignalSynchronizationObjectFromGpu to signal a monitored fence.
old-location: display\d3dkmt_signalsynchronizationobjectfromgpu.htm
ms.assetid: 09190DCC-5F88-4C49-89B3-9063707E3F15
ms.date: 05/10/2018
ms.keywords: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU, D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure [Display Devices], _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU, d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU, display.d3dkmt_signalsynchronizationobjectfromgpu
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
---

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure


## -description


<b>D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU</b> is used with <a href="https://msdn.microsoft.com/library/windows/hardware/dn906784">D3DKMTSignalSynchronizationObjectFromGpu</a> to signal a monitored fence.


## -struct-fields




### -field hContext

[in] A kernel-mode handle to the context stream.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the <b>hContext</b> member signals.


### -field MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to signal, each of which correspond to a synchronization object in <b>ObjectHandleArray</b>.


### -field Reserved

This member is reserved and should be set to zero.



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906784">D3DKMTSignalSynchronizationObjectFromGpu</a>
 

 

