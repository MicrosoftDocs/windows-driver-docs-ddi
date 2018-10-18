---
UID: NS:d3dhal._D3DHAL_DP2MULTIPLYTRANSFORM
title: "_D3DHAL_DP2MULTIPLYTRANSFORM"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2MULTIPLYTRANSFORM structure is used to modify the transform matrix for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2multiplytransform.htm
tech.root: display
ms.assetid: 3c7c0d40-a51e-4656-b262-233f0af8db0f
ms.date: 5/10/2018
ms.keywords: "*LPD3DHAL_DP2MULTIPLYTRANSFORM, D3DHAL_DP2MULTIPLYTRANSFORM, D3DHAL_DP2MULTIPLYTRANSFORM structure [Display Devices], LPD3DHAL_DP2MULTIPLYTRANSFORM, LPD3DHAL_DP2MULTIPLYTRANSFORM structure pointer [Display Devices], _D3DHAL_DP2MULTIPLYTRANSFORM, d3dhal/D3DHAL_DP2MULTIPLYTRANSFORM, d3dhal/LPD3DHAL_DP2MULTIPLYTRANSFORM, d3dstrct_5091bd4f-cace-4f31-8849-8f6ee65c7ec1.xml, display.d3dhal_dp2multiplytransform"
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
api_name:
-	D3DHAL_DP2MULTIPLYTRANSFORM
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2MULTIPLYTRANSFORM
---

# _D3DHAL_DP2MULTIPLYTRANSFORM structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2MULTIPLYTRANSFORM structure is used to modify the transform matrix for <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>.


## -struct-fields




### -field xfrmType

Specifies the current transform being modified.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_PROJECTION

</td>
<td>
Specifies the current projection transformation.

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_VIEW

</td>
<td>
Specifies the current view transformation.

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_WORLD

</td>
<td>
Specifies the current world transformation.

</td>
</tr>
</table>
 


### -field matrix

Specifies the matrix used to modify the current transform.


## -remarks



This structure is used with hardware transform and lighting and is used by the Direct3D runtime to inform the driver about modifications to the various transformation matrices.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545823">D3DHAL_DP2SETTRANSFORM</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

