---
UID: NS:d3dumddi._D3DDDIARG_SETPIXELSHADERCONST
title: "_D3DDDIARG_SETPIXELSHADERCONST"
author: windows-driver-content
description: The D3DDDIARG_SETPIXELSHADERCONST structure describes how to set the pixel shader constant registers.
old-location: display\d3dddiarg_setpixelshaderconst.htm
old-project: display
ms.assetid: 1c8cbbdc-ac2e-462e-9d5c-484305a41302
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_SETPIXELSHADERCONST, D3DDDIARG_SETPIXELSHADERCONST structure [Display Devices], D3DDDIARG_SETPIXELSHADERCONSTB, D3DDDIARG_SETPIXELSHADERCONSTI, UMDisplayDriver_param_Structs_b2bba0b4-f57a-48f6-a738-709fedfe678e.xml, _D3DDDIARG_SETPIXELSHADERCONST, d3dumddi/D3DDDIARG_SETPIXELSHADERCONST, display.d3dddiarg_setpixelshaderconst
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
-	D3DDDIARG_SETPIXELSHADERCONST
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETPIXELSHADERCONST
---

# _D3DDDIARG_SETPIXELSHADERCONST structure


## -description


The D3DDDIARG_SETPIXELSHADERCONST structure describes how to set the pixel shader constant registers. 


## -struct-fields




### -field Register

[in] The index of the first pixel shader constant register whose value is set.


### -field Count

[in] The number of constant registers to set and, therefore, the number of values in the array that is passed in the <i>pRegisters</i> parameter in the call to the user-mode display driver's <a href="https://msdn.microsoft.com/02710936-28df-4c8f-aa1e-bdff01155608">SetPixelShaderConst</a>, <a href="https://msdn.microsoft.com/fafc046e-0595-4901-bfb1-70bd980388bc">SetPixelShaderConstI</a>, or <a href="https://msdn.microsoft.com/6f7c8932-9332-4ff2-89ab-2f9a66783326">SetPixelShaderConstB</a> function.


## -remarks



The <b>Count</b> member specifies the following values, depending on the structure type that is used in the call to the <a href="https://msdn.microsoft.com/02710936-28df-4c8f-aa1e-bdff01155608">SetPixelShaderConst</a>, <a href="https://msdn.microsoft.com/fafc046e-0595-4901-bfb1-70bd980388bc">SetPixelShaderConstI</a>, or <a href="https://msdn.microsoft.com/6f7c8932-9332-4ff2-89ab-2f9a66783326">SetPixelShaderConstB</a> function: 

<ul>
<li>
Four-element, single-precision float vectors for the D3DDDIARG_SETPIXELSHADERCONST structure in the <a href="https://msdn.microsoft.com/02710936-28df-4c8f-aa1e-bdff01155608">SetPixelShaderConst</a> call.

</li>
<li>
Four-integer vectors for the D3DDDIARG_SETPIXELSHADERCONSTI structure in the <a href="https://msdn.microsoft.com/fafc046e-0595-4901-bfb1-70bd980388bc">SetPixelShaderConstI</a> call.

</li>
<li>
Boolean values for the D3DDDIARG_SETPIXELSHADERCONSTB structure in the <a href="https://msdn.microsoft.com/6f7c8932-9332-4ff2-89ab-2f9a66783326">SetPixelShaderConstB</a> call.

</li>
</ul>
The preceding structures are identical, as the following definitions show:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef D3DDDIARG_SETPIXELSHADERCONST D3DDDIARG_SETPIXELSHADERCONSTI;
typedef D3DDDIARG_SETPIXELSHADERCONST D3DDDIARG_SETPIXELSHADERCONSTB;</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/02710936-28df-4c8f-aa1e-bdff01155608">SetPixelShaderConst</a>



<a href="https://msdn.microsoft.com/6f7c8932-9332-4ff2-89ab-2f9a66783326">SetPixelShaderConstB</a>



<a href="https://msdn.microsoft.com/fafc046e-0595-4901-bfb1-70bd980388bc">SetPixelShaderConstI</a>
 

 

