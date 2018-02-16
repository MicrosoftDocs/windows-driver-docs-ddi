---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEDOMAINSHADER
title: PFND3D11_1DDI_CREATEDOMAINSHADER
author: windows-driver-content
description: Creates a domain shader.
old-location: display\createdomainshader_d3d11_1_.htm
old-project: display
ms.assetid: 74e6457f-4a99-4b19-9a7e-3ebac5aef48e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.createdomainshader_d3d11_1_, CreateDomainShader(D3D11_1) callback function [Display Devices], CreateDomainShader(D3D11_1), PFND3D11_1DDI_CREATEDOMAINSHADER, PFND3D11_1DDI_CREATEDOMAINSHADER, d3d10umddi/CreateDomainShader(D3D11_1), display.pfncreatedomainshader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	CreateDomainShader(D3D11_1)
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_CREATEDOMAINSHADER callback


## -description


Creates a domain shader.


## -prototype


````
PFND3D11_1DDI_CREATEDOMAINSHADER CreateDomainShader(D3D11_1);

VOID APIENTRY* CreateDomainShader(D3D11_1)(
             D3D10DDI_HDEVICE                         hDevice,
  _In_ const UINT                                     *pShaderCode,
             D3D10DDI_HSHADER                         hShader,
             D3D10DDI_HRTSHADER                       hRTShader,
  _In_ const D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES *pSignatures
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *pShaderCode [in]

 A pointer to an array of CONST UINT tokens that form the shader code. The first token in the shader code stream is always the version token. The next token in the stream is the length token that determines the end of the shader code stream. For more information about the format of Direct3D version 11 shader code, see the comments inside the D3d11tokenizedprogramformat.hpp header file that is included with the WDK. 


### -param D3D10DDI_HSHADER


### -param D3D10DDI_HRTSHADER


### -param *








#### - hDevice

 A handle to the display device (graphics context).


#### - hRTShader

 A handle to the domain shader that the driver should use when it calls back into the Direct3D runtime. 


#### - hShader

 A handle to the driver's private data for the domain shader. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatetessellationshadersize.md">CalcPrivateTessellationShaderSize(D3D11_1)</a>  function. The handle is  just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its tessellation-shader object. 


#### - pSignatures [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_tessellation_io_signatures.md">D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES</a> structure that forms the tessellation-shader's signature.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatetessellationshadersize.md">CalcPrivateTessellationShaderSize(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_tessellation_io_signatures.md">D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEDOMAINSHADER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

