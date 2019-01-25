---
UID: NS:d3dumddi._D3DDDIARG_CREATEVERTEXSHADERDECL
title: "_D3DDDIARG_CREATEVERTEXSHADERDECL" (d3dumddi.h)
description: The D3DDDIARG_CREATEVERTEXSHADERDECL structure specifies a shader handle to associate with the vertex shader declaration.
old-location: display\d3dddiarg_createvertexshaderdecl.htm
tech.root: display
ms.assetid: 510f8cda-922e-48de-b95e-daf972e906fa
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_CREATEVERTEXSHADERDECL, D3DDDIARG_CREATEVERTEXSHADERDECL structure [Display Devices], UMDisplayDriver_param_Structs_0f0f9192-2505-4b0f-99ee-7b0d64e8e340.xml, _D3DDDIARG_CREATEVERTEXSHADERDECL, d3dumddi/D3DDDIARG_CREATEVERTEXSHADERDECL, display.d3dddiarg_createvertexshaderdecl
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
-	D3DDDIARG_CREATEVERTEXSHADERDECL
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEVERTEXSHADERDECL
---

# _D3DDDIARG_CREATEVERTEXSHADERDECL structure


## -description


The D3DDDIARG_CREATEVERTEXSHADERDECL structure specifies a shader handle to associate with the vertex shader declaration.


## -struct-fields




### -field NumVertexElements

[in] The number of vertex elements in the array that is passed to the <i>pVertexElements</i> parameter in a call to the user-mode display driver's <a href="https://msdn.microsoft.com/00c53e81-93db-46b8-b65c-c8d62059452a">CreateVertexShaderDecl</a> function.


### -field ShaderHandle

[out] A handle to the vertex shader declaration.


## -remarks



The handle value in the <b>ShaderHandle</b> member is guaranteed to be nonzero. 

For more information about programming shader assemblers, see <a href="https://msdn.microsoft.com/c858766c-b414-4971-b4d9-23ec94aca8ea">Processing Shader Codes</a>.




## -see-also




<a href="https://msdn.microsoft.com/00c53e81-93db-46b8-b65c-c8d62059452a">CreateVertexShaderDecl</a>
 

 

