---
UID: NS:d3dumddi._D3DDDIARG_SETTRANSFORM
title: "_D3DDDIARG_SETTRANSFORM"
author: windows-driver-content
description: The D3DDDIARG_SETTRANSFORM structure describes how to set up a transform.
old-location: display\d3dddiarg_settransform.htm
old-project: display
ms.assetid: 1bd5c22e-c4c1-4b0a-b5ed-76e17cbe1aee
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_SETTRANSFORM, D3DDDIARG_SETTRANSFORM structure [Display Devices], UMDisplayDriver_param_Structs_719de83f-0830-4b1a-aa72-e3f58553c733.xml, _D3DDDIARG_SETTRANSFORM, d3dumddi/D3DDDIARG_SETTRANSFORM, display.d3dddiarg_settransform
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
-	D3DDDIARG_SETTRANSFORM
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETTRANSFORM
---

# _D3DDDIARG_SETTRANSFORM structure


## -description


The D3DDDIARG_SETTRANSFORM structure describes how to set up a transform. 


## -struct-fields




### -field TransformType

[in] A D3DTRANSFORMSTATETYPE-typed value that indicates the type of transform to set up. This member can be one of the following values.

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

[in] A D3DMATRIX structure that describes the matrix that is used to set up the transform. For more information about D3DMATRIX, see the Microsoft Windows SDK documentation.


## -remarks



The Microsoft Direct3D runtime uses D3DDDIARG_SETTRANSFORM in a call to the user-mode display driver <a href="https://msdn.microsoft.com/0e989ea4-3693-4c0b-86a5-96b865a0193f">SetTransform</a> function to inform the driver about various hardware transformation and lighting matrices. 




## -see-also




<a href="https://msdn.microsoft.com/0e989ea4-3693-4c0b-86a5-96b865a0193f">SetTransform</a>
 

 

