---
UID: NS:d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
title: _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU (d3dkmthk.h)
description: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU is used with D3DKMTSignalSynchronizationObjectFromCpu to enable a driver to signal a monitored fence.
old-location: display\d3dkmt_signalsynchronizationobjectfromcpu.htm
ms.assetid: 03B822CF-2FB0-412B-9F45-43756D8B4C19
ms.date: 05/10/2018
ms.keywords: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure [Display Devices], _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, display.d3dkmt_signalsynchronizationobjectfromcpu
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU"
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
- D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
---

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure


## -description


<b>D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromcpu">D3DKMTSignalSynchronizationObjectFromCpu</a> to enable a driver to signal a monitored fence.


## -struct-fields




### -field hDevice

[in] The handle to the device.


### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> and fence values in the <b>FenceValueArray</b>. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events to signal.


### -field FenceValueArray

[in] An array of 64 bit monitored fence values to signal, each corresponding to an object in the <b>ObjectHandleArray</b>.


### -field Flags

 

Flag options.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromcpu">D3DKMTSignalSynchronizationObjectFromCpu</a>
 

 

