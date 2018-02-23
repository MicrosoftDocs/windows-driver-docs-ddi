---
UID: NF:d3dkmthk.D3DKMTDestroyAllocation2
title: D3DKMTDestroyAllocation2 function
author: windows-driver-content
description: The D3DKMTDestroyAllocation2 function releases a resource, a list of allocations, or both.
old-location: display\d3dkmtdestroyallocation2.htm
old-project: display
ms.assetid: C66CD2FB-AD45-4666-ACD4-6555ED681935
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: d3dkmthk/D3DKMTDestroyAllocation2, display.d3dkmtdestroyallocation2, D3DKMTDestroyAllocation2, D3DKMTDestroyAllocation2 function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTDestroyAllocation2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTDestroyAllocation2 function


## -description


The <b>D3DKMTDestroyAllocation2</b> function releases a resource, a list of allocations, or both.


## -syntax


````
NTSTATUS APIENTRY D3DKMTDestroyAllocation2(
  _In_ const D3DKMT_DESTROYALLOCATION2 *pData
);
````


## -parameters




### -param D3DKMT_DESTROYALLOCATION2

TBD




#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroyallocation2.md">D3DKMT_DESTROYALLOCATION2</a> structure that contains information for releasing allocations.


## -returns




<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroyallocation.md">D3DKMTDestroyAllocation</a> returns one of the following values:

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
Allocations were successfully released.

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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroyallocation2.md">D3DKMT_DESTROYALLOCATION2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTDestroyAllocation2 function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

