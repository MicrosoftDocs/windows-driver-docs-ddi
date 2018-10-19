---
UID: NS:d3dkmthk._D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
title: "_D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2"
author: windows-driver-content
description: The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the D3DKMTWaitForSynchronizationObject2 function waits for to occur.
old-location: display\d3dkmt_waitforsynchronizationobject2.htm
ms.assetid: 934bfe32-b54b-477c-a5f8-714caa97f233
ms.date: 05/10/2018
ms.keywords: D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2, D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure [Display Devices], OpenGL_Structs_fb1ca5e1-799c-49c7-844d-25954fd0db64.xml, _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2, d3dkmthk/D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2, display.d3dkmt_waitforsynchronizationobject2
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
---

# _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure


## -description


The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547262">D3DKMTWaitForSynchronizationObject2</a> function waits for to occur. 


## -struct-fields




### -field hContext

[in] A kernel-mode handle to the context stream in which a wait for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for. The D3DDDI_MAX_OBJECT_WAITED_ON constant, which is defined as 32, indicates the maximum number of synchronization events that the context can wait for.


### -field Fence

A structure that contains information about a fence. The union in D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 can hold a Fence structure, which contains the following member:


### -field Fence.FenceValue

A 64-bit value that specifies the fence value to wait for. 


### -field Reserved

An array of 64-bit values that are reserved for future use. The union in D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 can hold this array. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547262">D3DKMTWaitForSynchronizationObject2</a>
 

 

