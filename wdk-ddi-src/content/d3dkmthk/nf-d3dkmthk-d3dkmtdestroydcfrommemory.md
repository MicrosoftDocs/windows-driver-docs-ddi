---
UID: NF:d3dkmthk.D3DKMTDestroyDCFromMemory
title: D3DKMTDestroyDCFromMemory function
author: windows-driver-content
description: The D3DKMTDestroyDCFromMemory function releases the display context.
old-location: display\d3dkmtdestroydcfrommemory.htm
ms.assetid: 1c34db7b-6153-40ec-9a9f-72b9c04c9f12
ms.date: 5/10/2018
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTDestroyDCFromMemory
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

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547878">D3DKMT_DESTROYDCFROMMEMORY</a> structure that contains handles to the display context and bitmap.


## -returns



<b>D3DKMTDestroyDCFromMemory</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The device context was successfully released.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547878">D3DKMT_DESTROYDCFROMMEMORY</a>
 

 

