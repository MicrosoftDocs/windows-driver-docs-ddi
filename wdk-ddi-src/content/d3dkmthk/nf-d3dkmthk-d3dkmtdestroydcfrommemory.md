---
UID: NF:d3dkmthk.D3DKMTDestroyDCFromMemory
title: D3DKMTDestroyDCFromMemory function (d3dkmthk.h)
description: The D3DKMTDestroyDCFromMemory function releases the display context.
old-location: display\d3dkmtdestroydcfrommemory.htm
ms.assetid: 1c34db7b-6153-40ec-9a9f-72b9c04c9f12
ms.date: 05/10/2018
ms.keywords: D3DKMTDestroyDCFromMemory, D3DKMTDestroyDCFromMemory function [Display Devices], OpenGL_Functions_2c70707b-7052-4f5f-8715-e2e61a7ab267.xml, d3dkmthk/D3DKMTDestroyDCFromMemory, display.d3dkmtdestroydcfrommemory
ms.topic: function
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTDestroyDCFromMemory
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTDestroyDCFromMemory function

## -description

The <b>D3DKMTDestroyDCFromMemory</b> function releases the display context.

## -parameters

### -param D3DKMT_DESTROYDCFROMMEMORY

*pData* [in]

 A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroydcfrommemory">D3DKMT_DESTROYDCFROMMEMORY</a> structure that contains handles to the display context and bitmap.

## -returns

<b>D3DKMTDestroyDCFromMemory</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The device context was successfully released.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroydcfrommemory">D3DKMT_DESTROYDCFROMMEMORY</a>
 

 

