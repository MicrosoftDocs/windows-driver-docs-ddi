---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATESAMPLERSIZE
title: PFND3D10DDI_CALCPRIVATESAMPLERSIZE (d3d10umddi.h)
description: The CalcPrivateSamplerSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a sampler.
old-location: display\calcprivatesamplersize.htm
ms.assetid: 7231ba65-f6ed-4b00-a61f-21d8fe26398f
ms.date: 05/10/2018
ms.keywords: CalcPrivateSamplerSize, CalcPrivateSamplerSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATESAMPLERSIZE, PFND3D10DDI_CALCPRIVATESAMPLERSIZE callback, UserModeDisplayDriverDx10_Functions_66c06423-c710-4b1f-8084-d42c79066909.xml, d3d10umddi/CalcPrivateSamplerSize, display.calcprivatesamplersize
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
 - "d3d10umddi/CalcPrivateSamplerSize"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateSamplerSize
product:
 - Windows
---

# PFND3D10DDI_CALCPRIVATESAMPLERSIZE callback function

## -description

The <b>CalcPrivateSamplerSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a sampler.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pSamplerDesc* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_sampler_desc">D3D10_DDI_SAMPLER_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateSamplerSize</b> returns the size of the memory region that the driver requires for creating a sampler.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_sampler_desc">D3D10_DDI_SAMPLER_DESC</a>

