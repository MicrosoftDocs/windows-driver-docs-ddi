---
UID: NS:d3dumddi._D3DDDIARG_CREATEVERTEXSHADERDECL
title: "_D3DDDIARG_CREATEVERTEXSHADERDECL"
author: windows-driver-content
description: The D3DDDIARG_CREATEVERTEXSHADERDECL structure specifies a shader handle to associate with the vertex shader declaration.
old-location: display\d3dddiarg_createvertexshaderdecl.htm
old-project: display
ms.assetid: 510f8cda-922e-48de-b95e-daf972e906fa
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, A, C, D, D3DDDIARG_CREATEVERTEXSHADERDECL, D3DDDIARG_CREATEVERTEXSHADERDECL structure [Display Devices], E, G, H, I, L, R, S, T, UMDisplayDriver_param_Structs_0f0f9192-2505-4b0f-99ee-7b0d64e8e340.xml, V, X, _, _D3DDDIARG_CREATEVERTEXSHADERDECL, d3dumddi/D3DDDIARG_CREATEVERTEXSHADERDECL, display.d3dddiarg_createvertexshaderdecl"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_CREATEVERTEXSHADERDECL
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEVERTEXSHADERDECL
---

# _D3DDDIARG_CREATEVERTEXSHADERDECL structure


## -description


The D3DDDIARG_CREATEVERTEXSHADERDECL structure specifies a shader handle to associate with the vertex shader declaration.


## -syntax


````
typedef struct _D3DDDIARG_CREATEVERTEXSHADERDECL {
  UINT   NumVertexElements;
  HANDLE ShaderHandle;
} D3DDDIARG_CREATEVERTEXSHADERDECL;
````


## -struct-fields




### -field NumVertexElements

[in] The number of vertex elements in the array that is passed to the <i>pVertexElements</i> parameter in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderdecl.md">CreateVertexShaderDecl</a> function.


### -field ShaderHandle

[out] A handle to the vertex shader declaration.


## -remarks



The handle value in the <b>ShaderHandle</b> member is guaranteed to be nonzero. 

For more information about programming shader assemblers, see <a href="https://msdn.microsoft.com/c858766c-b414-4971-b4d9-23ec94aca8ea">Processing Shader Codes</a>.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderdecl.md">CreateVertexShaderDecl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATEVERTEXSHADERDECL structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

