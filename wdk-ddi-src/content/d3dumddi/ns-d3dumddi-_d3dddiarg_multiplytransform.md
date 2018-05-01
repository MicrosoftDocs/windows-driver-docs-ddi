---
UID: NS:d3dumddi._D3DDDIARG_MULTIPLYTRANSFORM
title: "_D3DDDIARG_MULTIPLYTRANSFORM"
author: windows-driver-content
description: The D3DDDIARG_MULTIPLYTRANSFORM structure describes how to modify the current transform.
old-location: display\d3dddiarg_multiplytransform.htm
old-project: display
ms.assetid: 4f14532f-8937-4715-aa9f-e38f18179af7
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_MULTIPLYTRANSFORM, D3DDDIARG_MULTIPLYTRANSFORM structure [Display Devices], UMDisplayDriver_param_Structs_9bae119f-aead-46d7-8a10-18cd6e227102.xml, _D3DDDIARG_MULTIPLYTRANSFORM, d3dumddi/D3DDDIARG_MULTIPLYTRANSFORM, display.d3dddiarg_multiplytransform
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_MULTIPLYTRANSFORM
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_MULTIPLYTRANSFORM
---

# _D3DDDIARG_MULTIPLYTRANSFORM structure


## -description


The D3DDDIARG_MULTIPLYTRANSFORM structure describes how to modify the current transform. 


## -struct-fields




### -field TransformType

[in] A D3DTRANSFORMSTATETYPE-typed value that indicates the type of the transform that is being modified. This member can be one of the following values.

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
Projection transformation

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_VIEW

</td>
<td>
View transformation

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_WORLD

</td>
<td>
World transformation

</td>
</tr>
</table>
 


### -field Matrix

[in] A D3DMATRIX structure that describes the matrix that is used to modify the current transform. For more information about D3DMATRIX, see the Microsoft Windows SDK documentation.


## -remarks



The Microsoft Direct3D runtime uses D3DDDIARG_MULTIPLYTRANSFORM in a call to the user-mode display driver's <a href="https://msdn.microsoft.com/69d94062-5655-4d49-a116-7fa7e2b51a91">MultiplyTransform</a> function to inform the driver about modifications to the various transformation matrices.




## -see-also




<a href="https://msdn.microsoft.com/69d94062-5655-4d49-a116-7fa7e2b51a91">MultiplyTransform</a>
 

 

