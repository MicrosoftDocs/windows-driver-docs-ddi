---
UID: NS:d3d10umddi.D3D11DDI_SHADER_CAPS
title: D3D11DDI_SHADER_CAPS
author: windows-driver-content
description: The D3D11DDI_SHADER_CAPS structure contains display device shader capabilities.
old-location: display\d3d11ddi_shader_caps.htm
old-project: display
ms.assetid: 07ad70b0-9af2-4fbd-baff-aa91dd583a20
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11DDICAPS_SHADER_COMPUTE_PLUS_RAW_AND_STRUCTURED_BUFFERS_IN_SHADER_4_X (0x2), D3D11DDICAPS_SHADER_DOUBLES (0x1), D3D11DDI_SHADER_CAPS, D3D11DDI_SHADER_CAPS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_e0026993-2d6d-4478-8796-c423c841f7f8.xml, d3d10umddi/D3D11DDI_SHADER_CAPS, display.d3d11ddi_shader_caps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D11DDI_SHADER_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11DDI_SHADER_CAPS
---

# D3D11DDI_SHADER_CAPS structure


## -description


The D3D11DDI_SHADER_CAPS structure contains display device shader capabilities. 


## -syntax


````
typedef struct D3D11DDI_SHADER_CAPS {
  UINT Caps;
} D3D11DDI_SHADER_CAPS;
````


## -struct-fields




### -field Caps

[in] A valid bitwise <b>OR</b> of values that describe the shader capabilities of the display device. The Direct3D runtime supports the following values.



#### D3D11DDICAPS_SHADER_DOUBLES (0x1)

The display device supports shaders that can internally operate on double-precision floating-point numbers. However, these shaders can neither input nor output double values, and they cannot perform atomic operations on double values. Only operations that are internal to such a shader can use double values. The shader must form double values by combining input values at the start of the shader. The shader must break apart double values into multiple output values at the end of the shader.



#### D3D11DDICAPS_SHADER_COMPUTE_PLUS_RAW_AND_STRUCTURED_BUFFERS_IN_SHADER_4_X (0x2)

The display device supports compute shaders as well as raw and structured buffers. The runtime can successfully call the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createcomputeshader.md">CreateComputeShader</a> function to create a compute shader and the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview.md">CreateShaderResourceView(D3D11)</a> and <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a> functions to create raw and structured buffers. 

Drivers that run the <a href="https://msdn.microsoft.com/7d724751-761e-409c-8398-d1b5d58c057c">Direct3D version 11 pipeline</a> (the D3D11DDI_3DPIPELINELEVEL_11_0 value of the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_3dpipelinelevel.md">D3D11DDI_3DPIPELINELEVEL</a> enumeration) and greater must report this shader capability.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview.md">CreateShaderResourceView(D3D11)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createcomputeshader.md">CreateComputeShader</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_2ddicaps_type.md">D3D10_2DDICAPS_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDI_SHADER_CAPS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

