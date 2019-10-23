---
UID: NS:d3d10umddi.D3D11DDI_SHADER_CAPS
title: D3D11DDI_SHADER_CAPS (d3d10umddi.h)
description: The D3D11DDI_SHADER_CAPS structure contains display device shader capabilities.
old-location: display\d3d11ddi_shader_caps.htm
ms.assetid: 07ad70b0-9af2-4fbd-baff-aa91dd583a20
ms.date: 05/10/2018
ms.keywords: D3D11DDICAPS_SHADER_COMPUTE_PLUS_RAW_AND_STRUCTURED_BUFFERS_IN_SHADER_4_X (0x2), D3D11DDICAPS_SHADER_DOUBLES (0x1), D3D11DDI_SHADER_CAPS, D3D11DDI_SHADER_CAPS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_e0026993-2d6d-4478-8796-c423c841f7f8.xml, d3d10umddi/D3D11DDI_SHADER_CAPS, display.d3d11ddi_shader_caps
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D11DDI_SHADER_CAPS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_SHADER_CAPS is supported beginning with the Windows 7 operating system.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D11DDI_SHADER_CAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11DDI_SHADER_CAPS
---

# D3D11DDI_SHADER_CAPS structure


## -description


The D3D11DDI_SHADER_CAPS structure contains display device shader capabilities. 


## -struct-fields




### -field Caps

[in] A valid bitwise <b>OR</b> of values that describe the shader capabilities of the display device. The Direct3D runtime supports the following values.



#### D3D11DDICAPS_SHADER_DOUBLES (0x1)

The display device supports shaders that can internally operate on double-precision floating-point numbers. However, these shaders can neither input nor output double values, and they cannot perform atomic operations on double values. Only operations that are internal to such a shader can use double values. The shader must form double values by combining input values at the start of the shader. The shader must break apart double values into multiple output values at the end of the shader.



#### D3D11DDICAPS_SHADER_COMPUTE_PLUS_RAW_AND_STRUCTURED_BUFFERS_IN_SHADER_4_X (0x2)

The display device supports compute shaders as well as raw and structured buffers. The runtime can successfully call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createcomputeshader">CreateComputeShader</a> function to create a compute shader and the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview">CreateShaderResourceView(D3D11)</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a> functions to create raw and structured buffers. 

Drivers that run the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/pipelines-for-direct3d-version-11">Direct3D version 11 pipeline</a> (the D3D11DDI_3DPIPELINELEVEL_11_0 value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_3dpipelinelevel">D3D11DDI_3DPIPELINELEVEL</a> enumeration) and greater must report this shader capability.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createcomputeshader">CreateComputeShader</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview">CreateShaderResourceView(D3D11)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_2ddicaps_type">D3D10_2DDICAPS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>
 

 

