---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
title: PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE (d3d10umddi.h)
description: The CalcPrivateShaderResourceViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.
old-location: display\calcprivateshaderresourceviewsize.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function"]
ms.keywords: CalcPrivateShaderResourceViewSize, CalcPrivateShaderResourceViewSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE, PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback, UserModeDisplayDriverDx10_Functions_57360213-38f5-45aa-aadb-0bcdb674aec1.xml, d3d10umddi/CalcPrivateShaderResourceViewSize, display.calcprivateshaderresourceviewsize
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
 - PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
 - d3d10umddi/PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateShaderResourceViewSize
---

# PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function


## -description

The <b>CalcPrivateShaderResourceViewSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateShaderResourceView* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createshaderresourceview">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateShaderResourceViewSize</b> returns the size of the memory region that the driver requires for creating a shader resource view.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createshaderresourceview">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>
