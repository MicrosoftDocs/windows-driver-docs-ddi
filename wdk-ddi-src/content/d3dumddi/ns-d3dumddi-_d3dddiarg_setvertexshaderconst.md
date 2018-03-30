---
UID: NS:d3dumddi._D3DDDIARG_SETVERTEXSHADERCONST
title: "_D3DDDIARG_SETVERTEXSHADERCONST"
author: windows-driver-content
description: The D3DDDIARG_SETVERTEXSHADERCONST structure describes how to set vertex shader constant registers.
old-location: display\d3dddiarg_setvertexshaderconst.htm
old-project: display
ms.assetid: ac3c4609-094d-4003-a5ee-b609f7ec13e1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_SETVERTEXSHADERCONST, D3DDDIARG_SETVERTEXSHADERCONST structure [Display Devices], D3DDDIARG_SETVERTEXSHADERCONSTB, D3DDDIARG_SETVERTEXSHADERCONSTI, UMDisplayDriver_param_Structs_1d6878e5-ecbe-493c-bcbc-58eabc4b0972.xml, _D3DDDIARG_SETVERTEXSHADERCONST, d3dumddi/D3DDDIARG_SETVERTEXSHADERCONST, display.d3dddiarg_setvertexshaderconst
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
-	D3DDDIARG_SETVERTEXSHADERCONST
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETVERTEXSHADERCONST
---

# _D3DDDIARG_SETVERTEXSHADERCONST structure


## -description


The D3DDDIARG_SETVERTEXSHADERCONST structure describes how to set vertex shader constant registers. 


## -struct-fields




### -field Register

[in] The index of the first vertex shader constant register whose value is set.


### -field Count

[in] The number of constant registers to set and, therefore, the number of values in the array that is passed in the <i>pRegisters</i> parameter in the call to the user-mode display driver's <a href="https://msdn.microsoft.com/2dbde343-b10a-4357-a2b7-d6b1b1b868f2">SetVertexShaderConst</a>, <a href="https://msdn.microsoft.com/c245cfbd-0368-4a49-96a7-ac4cd14e2f5a">SetVertexShaderConstI</a>, or <a href="https://msdn.microsoft.com/41ca823e-4370-4cba-9129-067e25a43a69">SetVertexShaderConstB</a> function.


## -remarks



The <b>Count</b> member specifies the following values, depending on the structure type that is used in the call to the <a href="https://msdn.microsoft.com/2dbde343-b10a-4357-a2b7-d6b1b1b868f2">SetVertexShaderConst</a>, <a href="https://msdn.microsoft.com/c245cfbd-0368-4a49-96a7-ac4cd14e2f5a">SetVertexShaderConstI</a>, or <a href="https://msdn.microsoft.com/41ca823e-4370-4cba-9129-067e25a43a69">SetVertexShaderConstB</a> function: 

<ul>
<li>
Four-element, single-precision float vectors for the D3DDDIARG_SETVERTEXSHADERCONST structure in the <a href="https://msdn.microsoft.com/2dbde343-b10a-4357-a2b7-d6b1b1b868f2">SetVertexShaderConst</a> call.

</li>
<li>
Four-integer vectors for the D3DDDIARG_SETVERTEXSHADERCONSTI structure in the <a href="https://msdn.microsoft.com/c245cfbd-0368-4a49-96a7-ac4cd14e2f5a">SetVertexShaderConstI</a> call.

</li>
<li>
Boolean values for the D3DDDIARG_SETVERTEXSHADERCONSTB structure in the <a href="https://msdn.microsoft.com/41ca823e-4370-4cba-9129-067e25a43a69">SetVertexShaderConstB</a> call.

</li>
</ul>
The preceding structures are identical, as the following definitions show:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef D3DDDIARG_SETVERTEXSHADERCONST D3DDDIARG_SETVERTEXSHADERCONSTI;
typedef D3DDDIARG_SETVERTEXSHADERCONST D3DDDIARG_SETVERTEXSHADERCONSTB;</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/2dbde343-b10a-4357-a2b7-d6b1b1b868f2">SetVertexShaderConst</a>



<a href="https://msdn.microsoft.com/41ca823e-4370-4cba-9129-067e25a43a69">SetVertexShaderConstB</a>



<a href="https://msdn.microsoft.com/c245cfbd-0368-4a49-96a7-ac4cd14e2f5a">SetVertexShaderConstI</a>
 

 

