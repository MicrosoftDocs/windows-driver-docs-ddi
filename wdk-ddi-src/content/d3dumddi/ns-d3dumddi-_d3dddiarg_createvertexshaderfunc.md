---
UID: NS:d3dumddi._D3DDDIARG_CREATEVERTEXSHADERFUNC
title: "_D3DDDIARG_CREATEVERTEXSHADERFUNC"
author: windows-driver-content
description: The D3DDDIARG_CREATEVERTEXSHADERFUNC structure specifies a shader handle to associate with vertex shader code.
old-location: display\d3dddiarg_createvertexshaderfunc.htm
old-project: display
ms.assetid: 2517b7a9-76f5-46f6-9225-18081cd1d357
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDIARG_CREATEVERTEXSHADERFUNC, D3DDDIARG_CREATEVERTEXSHADERFUNC structure [Display Devices], UMDisplayDriver_param_Structs_cbcea02a-d591-4226-8896-f8392c4b67de.xml, _D3DDDIARG_CREATEVERTEXSHADERFUNC, d3dumddi/D3DDDIARG_CREATEVERTEXSHADERFUNC, display.d3dddiarg_createvertexshaderfunc
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
-	D3DDDIARG_CREATEVERTEXSHADERFUNC
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEVERTEXSHADERFUNC
---

# _D3DDDIARG_CREATEVERTEXSHADERFUNC structure


## -description


The D3DDDIARG_CREATEVERTEXSHADERFUNC structure specifies a shader handle to associate with vertex shader code.


## -syntax


````
typedef struct _D3DDDIARG_CREATEVERTEXSHADERFUNC {
  UINT   Size;
  HANDLE ShaderHandle;
} D3DDDIARG_CREATEVERTEXSHADERFUNC;
````


## -struct-fields




### -field Size

[in] The size, in bytes, of the vertex shader code that is passed to the <i>pCode</i> parameter in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderfunc.md">CreateVertexShaderFunc</a> function.


### -field ShaderHandle

[out] A handle to the vertex shader code.


## -remarks



For more information about programming shader assemblers, see <a href="https://msdn.microsoft.com/c858766c-b414-4971-b4d9-23ec94aca8ea">Processing Shader Codes</a>.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderfunc.md">CreateVertexShaderFunc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATEVERTEXSHADERFUNC structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

