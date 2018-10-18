---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATESHADERSIZE
title: PFND3D11_1DDI_CALCPRIVATESHADERSIZE
author: windows-driver-content
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.
old-location: display\calcprivateshadersize_d3d11_1_.htm
ms.assetid: e23c267f-41df-47a6-ae43-3bbcb48fd300
ms.date: 05/10/2018
ms.keywords: CalcPrivateShaderSize(D3D11_1), CalcPrivateShaderSize(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATESHADERSIZE, PFND3D11_1DDI_CALCPRIVATESHADERSIZE callback, d3d10umddi/CalcPrivateShaderSize(D3D11_1), display.calcprivateshadersize_d3d11_1_, display.pfncalcprivateshadersize
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
-	CalcPrivateShaderSize(D3D11_1)
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CALCPRIVATESHADERSIZE callback function


## -description


Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *pShaderCode [in]

A pointer to an array of CONST UINT tokens that make up the shader code.


### -param *

*pSignatures* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406324">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.


## -returns



The size of the memory region that the driver requires for creating a shader.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406324">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a>
 

 

