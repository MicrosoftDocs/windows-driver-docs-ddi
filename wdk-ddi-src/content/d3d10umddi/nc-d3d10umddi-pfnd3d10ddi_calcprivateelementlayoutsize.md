---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE
title: PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE (d3d10umddi.h)
description: The CalcPrivateElementLayoutSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an element layout.
old-location: display\calcprivateelementlayoutsize.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE callback function"]
ms.keywords: CalcPrivateElementLayoutSize, CalcPrivateElementLayoutSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE, PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE callback, UserModeDisplayDriverDx10_Functions_7c153781-eabd-4f5e-b949-0ac5c9e0d94b.xml, d3d10umddi/CalcPrivateElementLayoutSize, display.calcprivateelementlayoutsize
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
 - PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE
 - d3d10umddi/PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateElementLayoutSize
product:
 - Windows
---

# PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE callback function


## -description

The <i>CalcPrivateElementLayoutSize</i> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an element layout.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateElementLayout* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createelementlayout">D3D10DDIARG_CREATEELEMENTLAYOUT</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<i>CalcPrivateElementLayoutSize</i> returns the size of the memory region that the driver requires for creating an element layout.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createelementlayout">D3D10DDIARG_CREATEELEMENTLAYOUT</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>
