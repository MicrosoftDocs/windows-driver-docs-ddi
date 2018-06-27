---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: Creates a geometry shader with stream output.
old-location: display\creategeometryshaderwithstreamoutput_d3d11_1_.htm
old-project: display
ms.assetid: 1d06ef38-4eb9-4129-b409-74bbd1951f92
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CreateGeometryShaderWithStreamOutput(D3D11_1), CreateGeometryShaderWithStreamOutput(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback, d3d10umddi/CreateGeometryShaderWithStreamOutput(D3D11_1), display.creategeometryshaderwithstreamoutput_d3d11_1_, display.pfncreategeometryshaderwithstreamoutput
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CreateGeometryShaderWithStreamOutput(D3D11_1)
product:
- Windows
targetos: Windows
req.typenames:
---

# PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function


## -description


Creates a geometry shader with stream output.


## -parameters

### -param hDevice

 A handle to the display device (graphics context).


### -param hRTShader

 A handle to the geometry shader with stream output that the driver should use when it calls back into the Direct3D runtime.


### -param hShader

 A handle to the driver's private data for the geometry shader with stream output. The driver returns the size, in bytes, of the memory region that the Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/316e30b9-eb06-483c-a124-476b4308cf5f">CalcPrivateGeometryShaderWithStreamOutput(D3D11_1)</a>  function. The handle is  just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader object.


### -param pOutput [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542057">D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a> structure that describes the parameters that the user-mode display driver uses to create a geometry shader with stream output.


### -param pSignatures [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406324">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a> structure that forms the shader's signature.


## -returns



The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -see-also




<a href="https://msdn.microsoft.com/316e30b9-eb06-483c-a124-476b4308cf5f">CalcPrivateGeometryShaderWithStreamOutput(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542057">D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406324">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

