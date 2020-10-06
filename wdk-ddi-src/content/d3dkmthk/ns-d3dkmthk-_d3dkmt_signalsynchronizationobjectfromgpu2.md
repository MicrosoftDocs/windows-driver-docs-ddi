---
UID: NS:d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
title: _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 (d3dkmthk.h)
description: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 is used with D3DKMTSignalSynchronizationObjectFromGpu2 to signal a monitored fence.
old-location: display\d3dkmt_signalsynchronizationobjectfromgpu2.htm
ms.assetid: 3F9A7BBE-BFC2-47B9-856A-0B6930717A36
ms.date: 05/10/2018
keywords: ["D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure"]
ms.keywords: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2, D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure [Display Devices], _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2, d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2, display.d3dkmt_signalsynchronizationobjectfromgpu2
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
req.typenames: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
f1_keywords:
 - _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
 - d3dkmthk/_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
 - D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
 - d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
---

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure


## -description

<b>D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</b> is used with <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu2">D3DKMTSignalSynchronizationObjectFromGpu2</a> to signal a monitored fence.

## -struct-fields

### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.

### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for.

### -field Flags

[in] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_signalflags">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.

### -field BroadcastContextCount

[in] The number of contexts this signal operation will be broadcast to.

### -field BroadcastContextArray

[in] An array of kernel-mode handles to the context streams in which a signal for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted. The synchronization events are considered signaled only when all broadcast contexts reach the signal insertion point.

### -field FenceValue

[in] A 64-bit value that specifies the current fence value of the GPU synchronization object. This value applies only if the GPU synchronization object is of type <b>D3DDDI_FENCE</b>.

### -field CpuEventHandle

[in] The handle of an event object that will be signaled when the signal command is processed. This member must be set only when <b>Flags.EnqueueCpuEvent</b> is specified.

### -field MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to signal, each of which correspond to a synchronization object in <b>ObjectHandleArray</b>.

### -field Reserved

This member is reserved and should be set to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu2">D3DKMTSignalSynchronizationObjectFromGpu2</a>