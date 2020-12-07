---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE
title: PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE (d3d10umddi.h)
description: The CalcPrivateBlendStateSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.
old-location: display\calcprivateblendstatesize.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE callback function"]
ms.keywords: CalcPrivateBlendStateSize, CalcPrivateBlendStateSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE, PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE callback, UserModeDisplayDriverDx10_Functions_bb7c2ca6-61c8-4f54-a635-4ec9fb539837.xml, d3d10umddi/CalcPrivateBlendStateSize, display.calcprivateblendstatesize
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
 - PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE
 - d3d10umddi/PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateBlendStateSize
product:
 - Windows
---

# PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE callback function


## -description

The <b>CalcPrivateBlendStateSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pBlendDesc* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_blend_desc">D3D10_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateBlendStateSize</b> returns the size of the memory region that the driver requires for creating a blend state.

## -remarks

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_blend_desc">D3D10_DDI_BLEND_DESC</a>
