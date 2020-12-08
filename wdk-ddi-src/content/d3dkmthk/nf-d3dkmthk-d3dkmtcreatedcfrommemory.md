---
UID: NF:d3dkmthk.D3DKMTCreateDCFromMemory
title: D3DKMTCreateDCFromMemory function (d3dkmthk.h)
description: The D3DKMTCreateDCFromMemory function creates a display context from a specified block of memory.
old-location: display\d3dkmtcreatedcfrommemory.htm
ms.date: 05/10/2018
keywords: ["D3DKMTCreateDCFromMemory function"]
ms.keywords: D3DKMTCreateDCFromMemory, D3DKMTCreateDCFromMemory callback function [Display Devices], OpenGL_Functions_676f0d3e-5a5a-48d5-9092-88ac897a73b8.xml, PFND3DKMT_CREATEDCFROMMEMORY, PFND3DKMT_CREATEDCFROMMEMORY callback, d3dkmthk/D3DKMTCreateDCFromMemory, display.d3dkmtcreatedcfrommemory
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTCreateDCFromMemory
 - d3dkmthk/D3DKMTCreateDCFromMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTCreateDCFromMemory
---

# D3DKMTCreateDCFromMemory function


## -description

The <b>D3DKMTCreateDCFromMemory</b> function creates a display context from a specified block of memory.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createdcfrommemory">D3DKMT_CREATEDCFROMMEMORY</a> structure that describes parameters for creating a display context.

## -returns

<b>D3DKMTCreateDCFromMemory</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The display context was successfully created.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -remarks

The kernel controls the memory referenced by the display context created by the <b>D3DKMTCreateDCFromMemory</b> function. You must call the  <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroydcfrommemory">D3DKMTDestoryDCFromMemory</a> function to free the memory referenced by the display context. Any  other approach  to free this memory will fail. 

During the execution of the <b>D3DKMTCreateDCFromMemory</b> function, the kernel locks and probes the referenced memory by performing a non-thread safe write to each page in the memory. No other threads in your process should be trying to access any part of this memory for the duration of the <b>D3DKMTCreateDCFromMemory</b> call; otherwise, the results will be undefined.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createdcfrommemory">D3DKMT_CREATEDCFROMMEMORY</a>
