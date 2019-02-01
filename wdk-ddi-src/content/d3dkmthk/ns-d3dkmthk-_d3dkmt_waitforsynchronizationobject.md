---
UID: NS:d3dkmthk._D3DKMT_WAITFORSYNCHRONIZATIONOBJECT
title: _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the D3DKMTWaitForSynchronizationObject function waits for to occur.
old-location: display\d3dkmt_waitforsynchronizationobject.htm
ms.assetid: 47d0330e-5413-4729-b103-c1a4d6c648e1
ms.date: 05/10/2018
ms.keywords: D3DKMT_WAITFORSYNCHRONIZATIONOBJECT, D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure [Display Devices], OpenGL_Structs_5498c651-0ef6-4114-9821-de193980f879.xml, _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT, d3dkmthk/D3DKMT_WAITFORSYNCHRONIZATIONOBJECT, display.d3dkmt_waitforsynchronizationobject
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_WAITFORSYNCHRONIZATIONOBJECT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_WAITFORSYNCHRONIZATIONOBJECT
---

# _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure


## -description


The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547255">D3DKMTWaitForSynchronizationObject</a> function waits for to occur. 


## -struct-fields




### -field hContext

[in] A kernel-mode handle to the context stream in which a wait for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for. The D3DDDI_MAX_OBJECT_WAITED_ON constant, which is defined as 32, indicates the maximum number of synchronization events that the context can wait for.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547255">D3DKMTWaitForSynchronizationObject</a>
 

 

