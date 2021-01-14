---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT (d3d10umddi.h)
description: The CreateGeometryShaderWithStreamOutput function creates a geometry shader with stream output.
old-location: display\creategeometryshaderwithstreamoutput.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function"]
ms.keywords: CreateGeometryShaderWithStreamOutput, CreateGeometryShaderWithStreamOutput callback function [Display Devices], PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback, UserModeDisplayDriverDx10_Functions_e7442d66-9ff1-4ac0-b72d-cf23a1f34017.xml, d3d10umddi/CreateGeometryShaderWithStreamOutput, display.creategeometryshaderwithstreamoutput
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
 - d3d10umddi/PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
---

# PFND3D10DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function


## -description

The <b>CreateGeometryShaderWithStreamOutput</b> function creates a geometry shader with stream output.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateGeometryWithShaderOutput* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_creategeometryshaderwithstreamoutput">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a> structure that describes the parameters that the user-mode display driver uses to create a geometry shader with stream output.

### -param Arg3

*hShader* [in]

A handle to the driver's private data for the geometry shader with stream output. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput">CalcPrivateGeometryShaderWithStreamOutput</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader object.

### -param Arg4

*hRTShader* [in]

A handle to the geometry shader with stream output that the driver should use anytime it calls back into the Direct3D runtime.

### -param Arg5

*pSignatures* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_stage_io_signatures">D3D10DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput">CalcPrivateGeometryShaderWithStreamOutput</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_creategeometryshaderwithstreamoutput">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_stage_io_signatures">D3D10DDIARG_STAGE_IO_SIGNATURES</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

