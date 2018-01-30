---
UID: NS:d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
title: "_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2"
author: windows-driver-content
description: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 is used with D3DKMTSignalSynchronizationObjectFromGpu2 to signal a monitored fence.
old-location: display\d3dkmt_signalsynchronizationobjectfromgpu2.htm
old-project: display
ms.assetid: 3F9A7BBE-BFC2-47B9-856A-0B6930717A36
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2, D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure [Display Devices], display.d3dkmt_signalsynchronizationobjectfromgpu2, d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2, _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
product: Windows
targetos: Windows
req.typenames: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
---

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure


## -description


<b>D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu2.md">D3DKMTSignalSynchronizationObjectFromGpu2</a> to signal a monitored fence.


## -syntax


````
typedef struct _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 {
  UINT                 ObjectCount;
  const D3DKMT_HANDLE  *ObjectHandleArray;
  D3DDDICB_SIGNALFLAGS Flags;
  ULONG                BroadcastContextCount;
  const D3DKMT_HANDLE  *BroadcastContextArray;
  union {
    UINT64       FenceValue;
    HANDLE       CpuEventHandle;
    const UINT64 *MonitoredFenceValueArray;
    UINT64       Reserved[8];
  };
} D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2;
````


## -struct-fields




### -field FenceValue

[in] A 64-bit value that specifies the current fence value of the GPU synchronization object. This value applies only if the GPU synchronization object is of type <b>D3DDDI_FENCE</b>.


### -field CpuEventHandle

[in] The handle of an event object that will be signaled when the signal command is processed. This member must be set only when <b>Flags.EnqueueCpuEvent</b> is specified.


### -field MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to signal, each of which correspond to a synchronization object in <b>ObjectHandleArray</b>.


### -field Reserved

This member is reserved and should be set to zero.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for.


### -field Flags

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_signalflags.md">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.


### -field BroadcastContextCount

[in] The number of contexts this signal operation will be broadcast to.


### -field BroadcastContextArray

[in] An array of kernel-mode handles to the context streams in which a signal for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted. The synchronization events are considered signaled only when all broadcast contexts reach the signal insertion point.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu2.md">D3DKMTSignalSynchronizationObjectFromGpu2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

