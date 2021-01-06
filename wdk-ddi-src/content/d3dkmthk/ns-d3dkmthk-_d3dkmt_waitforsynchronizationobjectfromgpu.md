---
UID: NS:d3dkmthk._D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
title: _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU (d3dkmthk.h)
description: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU is used with D3DKMTWaitForSynchronizationObjectFromGpu to wait for a monitored fence to reach a certain value.
old-location: display\d3dkmt_waitforsynchronizationobjectfromgpu.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure"]
ms.keywords: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU, D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure [Display Devices], _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU, d3dkmthk/D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU, display.d3dkmt_waitforsynchronizationobjectfromgpu
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
f1_keywords:
 - _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
 - d3dkmthk/_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
 - D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
 - d3dkmthk/D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
---

# _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure


## -description

<b>D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</b> is used with <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtwaitforsynchronizationobjectfromgpu">D3DKMTWaitForSynchronizationObjectFromGpu</a> to wait for a monitored fence to reach a certain value.

## -struct-fields

### -field hContext

[in] A kernel-mode handle to the context stream in which a wait for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted.

### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.

### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for.

### -field MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to wait for, each value corresponding to a synchronization object in <b>ObjectHandleArray</b>.

### -field FenceValue

[in] Fence value to wait for when the input object is of type <b>D3DDDI_FENCE</b>.

### -field Reserved

This member is reserved and should be set to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtwaitforsynchronizationobjectfromgpu">D3DKMTWaitForSynchronizationObjectFromGpu</a>
