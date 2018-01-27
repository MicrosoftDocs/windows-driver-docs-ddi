---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEGEOMETRYSHADER
title: PFND3D11_1DDI_CREATEGEOMETRYSHADER
author: windows-driver-content
description: Creates a geometry shader.
old-location: display\creategeometryshader_d3d11_1_.htm
old-project: display
ms.assetid: A0C3826D-E4F3-4169-A899-41C11006DE69
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.creategeometryshader_d3d11_1_, CreateGeometryShader(D3D11_1) callback function [Display Devices], CreateGeometryShader(D3D11_1), PFND3D11_1DDI_CREATEGEOMETRYSHADER, PFND3D11_1DDI_CREATEGEOMETRYSHADER, d3d10umddi/CreateGeometryShader(D3D11_1)
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
-	CreateGeometryShader(D3D11_1)
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_CREATEGEOMETRYSHADER callback


## -description


Creates a geometry shader.


## -prototype


````
PFND3D11_1DDI_CREATEGEOMETRYSHADER CreateGeometryShader(D3D11_1);

VOID APIENTRY CreateGeometryShader(D3D11_1)(
  _In_       D3D10DDI_HDEVICE                  hDevice,
  _In_ const UINT                              *pShaderCode,
  _In_       D3D10DDI_HSHADER                  hShader,
  _In_       D3D10DDI_HRTSHADER                hRTShader,
  _In_ const D3D11_1DDIARG_STAGE_IO_SIGNATURES *pSignatures
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *pShaderCode



### -param D3D10DDI_HSHADER



### -param D3D10DDI_HRTSHADER



### -param *






#### - hShader [in]

 A handle to the driver's private data for the geometry shader. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateshadersize.md">CalcPrivateShaderSize(D3D11_1)</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader object.


#### - hRTShader [in]

 A handle to the geometry shader that the driver should use when it calls back into the Direct3D runtime.


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pSignatures [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_stage_io_signatures.md">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.


#### - pShaderCode [in]

 A pointer to an array of CONST UINT tokens that make up the shader code. The first token in the shader code stream is always the version token. The next token in the stream is the length token that determines the end of the shader code stream. For more information about the format of Direct3D version 11.1 shader code, see the comments inside the D3d10tokenizedprogramformat.hpp header file that is included with the WDK.


## -returns


The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks



    The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is incorrect; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshader.md">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.
   



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_stage_io_signatures.md">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshader.md">DestroyShader</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateshadersize.md">CalcPrivateShaderSize(D3D11_1)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEGEOMETRYSHADER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

