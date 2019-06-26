---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE
title: PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE (d3d10umddi.h)
description: The CalcPrivateTessellationShaderSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a hull or domain shader.
old-location: display\calcprivatetessellationshadersize.htm
ms.assetid: 604d7475-4696-429e-a645-781931509bb6
ms.date: 05/10/2018
ms.keywords: CalcPrivateTessellationShaderSize, CalcPrivateTessellationShaderSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE, PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE callback, UserModeDisplayDriverDx11_Functions_a669f28f-b275-4265-b6ae-5c3526d81b46.xml, d3d10umddi/CalcPrivateTessellationShaderSize, display.calcprivatetessellationshadersize
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateTessellationShaderSize is supported beginning with the Windows 7 operating system.
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
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- CalcPrivateTessellationShaderSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE callback function


## -description


The <b>CalcPrivateTessellationShaderSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a hull or domain shader.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *pShaderCode


### -param *

*pCode* [in]

 An array of CONST UINT tokens that form the hull-shader code or domain-shader code.

### -param *

*pSignatures* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_tessellation_io_signatures">D3D11DDIARG_TESSELLATION_IO_SIGNATURES</a> structure that forms the hull or domain shader's signature.


## -returns



<b>CalcPrivateTessellationShaderSize</b> returns the size of the memory region that the driver requires to create a hull or domain shader.




## -remarks



The Direct3D runtime calls the driver's <b>CalcPrivateTessellationShaderSize</b> function to calculate the size of the memory region for a hull or domain shader. This is similar to the way that the Direct3D runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize">CalcPrivateShaderSize</a> function to calculate the size of the memory region for a pixel, vertex, or geometry shader (that is, a geometry shader without stream output).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize">CalcPrivateShaderSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_tessellation_io_signatures">D3D11DDIARG_TESSELLATION_IO_SIGNATURES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>
 

 

