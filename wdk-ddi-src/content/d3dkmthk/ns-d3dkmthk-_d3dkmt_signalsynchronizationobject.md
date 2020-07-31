---
UID: NS:d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECT
title: _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the D3DKMTSignalSynchronizationObject function signals.
old-location: display\d3dkmt_signalsynchronizationobject.htm
ms.assetid: 13368ea2-dd2e-48af-b528-097104dffb60
ms.date: 05/10/2018
keywords: ["_D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure"]
ms.keywords: D3DKMT_SIGNALSYNCHRONIZATIONOBJECT, D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure [Display Devices], OpenGL_Structs_8a7c1832-e93f-47d3-b5ec-b5bea7f3321a.xml, _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT, d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECT, display.d3dkmt_signalsynchronizationobject
f1_keywords:
 - "d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECT"
 - "D3DKMT_SIGNALSYNCHRONIZATIONOBJECT"
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
- D3DKMT_SIGNALSYNCHRONIZATIONOBJECT
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SIGNALSYNCHRONIZATIONOBJECT
---

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure


## -description


The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobject">D3DKMTSignalSynchronizationObject</a> function signals. 


## -struct-fields




### -field hContext

[in] A kernel-mode handle to a context that signals the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member signals. The D3DDDI_MAX_OBJECT_SIGNALED constant, which is defined as 32, indicates the maximum number of synchronization events that the context can signal. 


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_signalflags">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_signalflags">D3DDDICB_SIGNALFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobject">D3DKMTSignalSynchronizationObject</a>
 

 

