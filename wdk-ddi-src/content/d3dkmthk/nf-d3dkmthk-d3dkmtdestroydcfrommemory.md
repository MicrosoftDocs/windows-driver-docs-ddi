---
UID: NF:d3dkmthk.D3DKMTDestroyDCFromMemory
title: D3DKMTDestroyDCFromMemory function
author: windows-driver-content
description: The D3DKMTDestroyDCFromMemory function releases the display context.
old-location: display\d3dkmtdestroydcfrommemory.htm
old-project: display
ms.assetid: 1c34db7b-6153-40ec-9a9f-72b9c04c9f12
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: OpenGL_Functions_2c70707b-7052-4f5f-8715-e2e61a7ab267.xml, D3DKMTDestroyDCFromMemory, display.d3dkmtdestroydcfrommemory, d3dkmthk/D3DKMTDestroyDCFromMemory, D3DKMTDestroyDCFromMemory function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTDestroyDCFromMemory
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTDestroyDCFromMemory function


## -description


The <b>D3DKMTDestroyDCFromMemory</b> function releases the display context.


## -syntax


````
NTSTATUS D3DKMTDestroyDCFromMemory(
  _In_ const D3DKMT_DESTROYDCFROMMEMORY *pData
);
````


## -parameters




### -param D3DKMT_DESTROYDCFROMMEMORY

TBD



#### - pData [in]

 A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroydcfrommemory.md">D3DKMT_DESTROYDCFROMMEMORY</a> structure that contains handles to the display context and bitmap.


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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroydcfrommemory.md">D3DKMT_DESTROYDCFROMMEMORY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTDestroyDCFromMemory function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

