---
UID: NS:d3dkmthk._D3DKMT_VIDMM_ESCAPE
title: _D3DKMT_VIDMM_ESCAPE (d3dkmthk.h)
description: The D3DKMT_VIDMM_ESCAPE structure describes how to control the video memory manager (which is part of Dxgkrnl.sys) in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_vidmm_escape.htm
ms.assetid: b9fb9960-9e6a-4c41-9c40-8ad307f83f0e
ms.date: 05/10/2018
keywords: ["_D3DKMT_VIDMM_ESCAPE structure"]
ms.keywords: D3DKMT_VIDMM_ESCAPE, D3DKMT_VIDMM_ESCAPE structure [Display Devices], OpenGL_Structs_9a9c243b-b99e-43f2-a749-afbb839fb7c0.xml, _D3DKMT_VIDMM_ESCAPE, d3dkmthk/D3DKMT_VIDMM_ESCAPE, display.d3dkmt_vidmm_escape
f1_keywords:
 - "d3dkmthk/D3DKMT_VIDMM_ESCAPE"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
- D3DKMT_VIDMM_ESCAPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_VIDMM_ESCAPE
dev_langs:
 - c++
ms.custom: 19H1
---

# _D3DKMT_VIDMM_ESCAPE structure


## -description


<b>Do not use the D3DKMT_VIDMM_ESCAPE structure; it is for testing purposes only.</b>

The D3DKMT_VIDMM_ESCAPE structure describes how to control the video memory manager (which is part of Dxgkrnl.sys) in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtescape">D3DKMTEscape</a> function.


## -struct-fields




### -field Type


### -field SetFault



#### SplitPoin



#### HotAddMemory


### -field SetFault.ProbeAndLock


### -field SetFault.SplitPoint

 


### -field SetFault.NoDemotion

 


### -field SetFault.SwizzlingAperture


### -field SetFault.PagingPathLockSubRange


### -field SetFault.PagingPathLockMinRange


### -field SetFault.ComplexLock


### -field SetFault.FailVARotation


### -field SetFault.NoWriteCombined


### -field SetFault.NoPrePatching


### -field SetFault.AlwaysRepatch


### -field SetFault.ExpectPreparationFailure


### -field SetFault.FailUserModeVAMapping


### -field SetFault.NeverDiscardOfferedAllocation


### -field SetFault.AlwaysDiscardOfferedAllocation


### -field SetFault.Reserved


### -field SetFault.Value


### -field Evict


### -field Evict.ResourceHandle

 


### -field Evict.AllocationHandle

 


### -field Evict.hProcess

A handle to the process.


### -field EvictByNtHandle


### -field EvictByNtHandle.NtHandle

 


### -field GetVads

 


### -field GetVads.GetNumVads

 


### -field GetVads.GetNumVads.NumVads

 


### -field GetVads.GetVad

 


### -field GetVads.GetVadRange

 


### -field GetVads.GetGpuMmuCaps

The GPU memory management capabilities.


### -field GetVads.GetPte

 


### -field GetVads.GetSegmentCaps

 


### -field GetVads.Command

 


### -field GetVads.Status

 


### -field SetBudget

 


### -field SetBudget.LocalMemoryBudget

 


### -field SetBudget.SystemMemoryBudget

 


### -field SuspendProcess

 


### -field SuspendProcess.hProcess

A handle to the process.


### -field SuspendProcess.bAllowWakeOnSubmission

 


### -field ResumeProcess

 


### -field ResumeProcess.hProcess

A handle to the process.

### -field GetBudget

 


### -field GetBudget.NumBytesToTrim

 


### -field SetTrimIntervals

 


### -field SetTrimIntervals.MinTrimInterval

 


### -field SetTrimIntervals.MaxTrimInterval

 


### -field SetTrimIntervals.IdleTrimInterval

 


### -field EvictByCriteria

 


### -field Wake

 


### -field Wake.bFlush

 


### -field Defrag

 


### -field Defrag.Operation

 


### -field Defrag.SegmentId

 


### -field Defrag.TotalCommitted

 


### -field Defrag.TotalFree

 


### -field Defrag.LargestGapBefore

 


### -field Defrag.LargestGapAfter

 

### -field DelayExecution
 
### -field DelayExecution.hPagingQueue
 
### -field DelayExecution.Milliseconds
 
### -field DelayExecution.PagingFenceValue


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtescape">D3DKMTEscape</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_escape">D3DKMT_ESCAPE</a>
 

 

