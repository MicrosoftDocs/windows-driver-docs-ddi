---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: Creates a geometry shader with stream output.
old-location: display\creategeometryshaderwithstreamoutput_d3d11_1_.htm
old-project: display
ms.assetid: 1d06ef38-4eb9-4129-b409-74bbd1951f92
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.creategeometryshaderwithstreamoutput_d3d11_1_, CreateGeometryShaderWithStreamOutput(D3D11_1) callback function [Display Devices], CreateGeometryShaderWithStreamOutput(D3D11_1), PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, d3d10umddi/CreateGeometryShaderWithStreamOutput(D3D11_1), display.pfncreategeometryshaderwithstreamoutput
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
-	CreateGeometryShaderWithStreamOutput(D3D11_1)
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback


## -description


Creates a geometry shader with stream output.


## -prototype


````
PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT CreateGeometryShaderWithStreamOutput(D3D11_1);

VOID APIENTRY* CreateGeometryShaderWithStreamOutput(D3D11_1)(
             D3D10DDI_HDEVICE                                 hDevice,
  _In_ const D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT *pOutput,
             D3D10DDI_HSHADER                                 hShader,
             D3D10DDI_HRTSHADER                               hRTShader,
  _In_ const D3D11_1DDIARG_STAGE_IO_SIGNATURES                *pSignatures
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








### -param D3D10DDI_HSHADER


### -param D3D10DDI_HRTSHADER


#### - hDevice

 A handle to the display device (graphics context).


#### - hRTShader

 A handle to the geometry shader with stream output that the driver should use when it calls back into the Direct3D runtime. 


#### - hShader

 A handle to the driver's private data for the geometry shader with stream output. The driver returns the size, in bytes, of the memory region that the Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput(D3D11_1)</a>  function. The handle is  just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader object. 


#### - pOutput [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_creategeometryshaderwithstreamoutput.md">D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a> structure that describes the parameters that the user-mode display driver uses to create a geometry shader with stream output. 


#### - pSignatures [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_stage_io_signatures.md">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a> structure that forms the shader's signature.


## -returns



The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_creategeometryshaderwithstreamoutput.md">D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_stage_io_signatures.md">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput(D3D11_1)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

