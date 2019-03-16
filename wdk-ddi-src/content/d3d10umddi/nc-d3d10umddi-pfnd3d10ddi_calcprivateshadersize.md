---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATESHADERSIZE
title: PFND3D10DDI_CALCPRIVATESHADERSIZE (d3d10umddi.h)
description: The CalcPrivateShaderSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.
old-location: display\calcprivateshadersize.htm
ms.assetid: 76cdddb0-b927-4547-ae1d-f5105905633b
ms.date: 05/10/2018
ms.keywords: CalcPrivateShaderSize, CalcPrivateShaderSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATESHADERSIZE, PFND3D10DDI_CALCPRIVATESHADERSIZE callback, UserModeDisplayDriverDx10_Functions_32a6a3cc-1a0d-4a20-a985-0e0e50daa914.xml, d3d10umddi/CalcPrivateShaderSize, display.calcprivateshadersize
ms.topic: callback
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- CalcPrivateShaderSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CALCPRIVATESHADERSIZE callback function


## -description


The <b>CalcPrivateShaderSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.


## -parameters




### -param Arg1

*hDevice* [in] 

A handle to the display device (graphics context).

### -param 

*pShaderCode* [in] 

An array of CONST UINT tokens that make up the shader code.

### -param *

*pSignatures* [in] 

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.


## -returns



<i>CalcPrivateShaderSize</i> returns the size of the memory region that the driver requires for creating a shader.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>
 

 

