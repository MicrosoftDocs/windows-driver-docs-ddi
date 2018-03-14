---
UID: NS:d3dumddi._D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2
title: "_D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2"
author: windows-driver-content
description: Describes the parameters that are required to set up signaling in a call to the pfnSignalSynchronizationObject2Cb function.
old-location: display\d3dddicb_signalsynchronizationobject2.htm
old-project: display
ms.assetid: cb8df28d-1d44-446b-83a8-b4191213973d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2 structure [Display Devices], _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2, d3dumddi/D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2, display.d3dddicb_signalsynchronizationobject2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dumddi.h
api_name:
-	D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2
product: Windows
targetos: Windows
req.typenames: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2
---

# _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2 structure


## -description


Describes the parameters that are required to set up signaling in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> function.


## -syntax


````
typedef struct _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2 {
  HANDLE               hContext;
  UINT                 ObjectCount;
  D3DKMT_HANDLE        ObjectHandleArray[D3DDDI_MAX_OBJECT_SIGNALED];
  D3DDDICB_SIGNALFLAGS Flags;
  ULONG                BroadcastContextCount;
  D3DKMT_HANDLE        BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  union {
    UINT64 FenceValue;
    HANDLE CpuEventHandle;
  };
} D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2;
````


## -struct-fields




### -field hContext

[in] A handle to a Direct3D context that signals the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array.


### -field ObjectHandleArray

[in] An array of handles to the synchronization events that the context that is specified by the <b>hContext</b> member signals. The <b>D3DDDI_MAX_OBJECT_SIGNALED</b> constant, which is defined as 32, indicates the maximum number of synchronization events that the context can signal.

All synchronization objects must be created on the same logical adapter as the  context specified by <b>hContext</b>.


### -field Flags

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_signalflags.md">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.


### -field BroadcastContextCount

[in] The number of contexts to broadcast this signal buffer to.


### -field BroadcastContext

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent kernel-mode handles to the additional contexts to broadcast the current signal command to. The <b>D3DDDI_MAX_BROADCAST_CONTEXT</b> constant, which is defined as 64, defines the maximum number of synchronization events that the context can signal to.

All contexts must be created for the same Direct3D device and the context that is specified by <b>hContext</b>.


#### - CpuEventHandle

[in] The handle of an event object that will be signaled when the signal command is processed. This member must be set only when <b>Flags</b>.<b>EnqueueCpuEvent</b> is specified.


#### - FenceValue

[in] A 64-bit value that specifies the current fence value of the GPU synchronization object.

This value applies only if the GPU synchronization object is of type <b>D3DDDI_FENCE</b>—namely, the <b>Type</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure has a value of <b>D3DDDI_FENCE</b>.


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_signalflags.md">D3DDDICB_SIGNALFLAGS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>



 

 


