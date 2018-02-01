---
UID: NS:d3dkmthk._D3DKMT_VIDMM_ESCAPE
title: "_D3DKMT_VIDMM_ESCAPE"
author: windows-driver-content
description: The D3DKMT_VIDMM_ESCAPE structure describes how to control the video memory manager (which is part of Dxgkrnl.sys) in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_vidmm_escape.htm
old-project: display
ms.assetid: b9fb9960-9e6a-4c41-9c40-8ad307f83f0e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: OpenGL_Structs_9a9c243b-b99e-43f2-a749-afbb839fb7c0.xml, d3dkmthk/D3DKMT_VIDMM_ESCAPE, _D3DKMT_VIDMM_ESCAPE, D3DKMT_VIDMM_ESCAPE structure [Display Devices], display.d3dkmt_vidmm_escape, D3DKMT_VIDMM_ESCAPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_VIDMM_ESCAPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_VIDMM_ESCAPE
---

# _D3DKMT_VIDMM_ESCAPE structure


## -description


<b>Do not use the D3DKMT_VIDMM_ESCAPE structure; it is for testing purposes only.</b>

The D3DKMT_VIDMM_ESCAPE structure describes how to control the video memory manager (which is part of Dxgkrnl.sys) in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a> function.


## -syntax


````
typedef struct _D3DKMT_VIDMM_ESCAPE {
  D3DKMT_VIDMMESCAPETYPE Type;
  union {
    struct {
      union {
        struct {
          ULONG ProbeAndLock  :1;
          ULONG SplitPoin  :1;
          ULONG HotAddMemory  :1;
          ULONG SwizzlingAperture  :1;
          ULONG PagingPathLockSubRange  :1;
          ULONG PagingPathLockMinRange  :1;
          ULONG ComplexLock  :1;
          ULONG FailVARotation  :1;
          ULONG NoWriteCombined  :1;
          ULONG NoPrePatching  :1;
          ULONG AlwaysRepatch  :1;
          ULONG ExpectPreparationFailure  :1;
          ULONG FailUserModeVAMapping  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
          ULONG NeverDiscardOfferedAllocation  :1;
          ULONG AlwaysDiscardOfferedAllocation  :1;
          ULONG Reserved  :17;
#else 
          ULONG Reserved  :19;
#endif 
        };
        ULONG Value;
      };
    } SetFault;
    struct {
      D3DKMT_HANDLE ResourceHandle;
      D3DKMT_HANDLE AllocationHandle;
    } Evict;
    struct {
      UINT64 NtHandle;
    } EvictByNtHandle;
  };
} D3DKMT_VIDMM_ESCAPE;
````


## -struct-fields




### -field SetFault



#### HotAddMemory



#### SplitPoin



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

 


### -field EvictByNtHandle



### -field EvictByNtHandle.NtHandle

 


### -field GetVads

 


### -field GetVads.GetNumVads

 


### -field GetVads.GetNumVads.NumVads

 


### -field GetVads.GetVad

 


### -field GetVads.GetVadRange

 


### -field GetVads.GetGpuMmuCaps

 


### -field GetVads.GetPte

 


### -field GetVads.GetSegmentCaps

 


### -field GetVads.Command

 


### -field GetVads.Status

 


### -field SetBudget

 


### -field SetBudget.LocalMemoryBudget

 


### -field SetBudget.SystemMemoryBudget

 


### -field SuspendProcess

 


### -field SuspendProcess.hProcess

 


### -field SuspendProcess.bAllowWakeOnSubmission

 


### -field ResumeProcess

 


### -field ResumeProcess.hProcess

 


### -field GetBudget

 


### -field GetBudget.NumBytesToTrim

 


### -field SetTrimIntervals

 


### -field SetTrimIntervals.MinTrimInterval

 


### -field SetTrimIntervals.MaxTrimInterval

 


### -field SetTrimIntervals.IdleTrimInterval

 


### -field Wake

 


### -field Wake.bFlush

 


### -field Defrag

 


### -field Defrag.Operation

 


### -field Defrag.SegmentId

 


### -field Defrag.TotalCommitted

 


### -field Defrag.TotalFree

 


### -field Defrag.LargestGapBefore

 


### -field Defrag.LargestGapAfter

 


### -field EvictByCriteria

 


### -field Type



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_escape.md">D3DKMT_ESCAPE</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_VIDMM_ESCAPE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

