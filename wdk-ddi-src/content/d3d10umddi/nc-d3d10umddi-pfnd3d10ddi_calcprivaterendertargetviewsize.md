---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE
title: PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE (d3d10umddi.h)
description: The CalcPrivateRenderTargetViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a render target view.
old-location: display\calcprivaterendertargetviewsize.htm
ms.assetid: 14d85e4a-960c-4438-9360-a4f2677603b8
ms.date: 05/10/2018
ms.keywords: CalcPrivateRenderTargetViewSize, CalcPrivateRenderTargetViewSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE, PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE callback, UserModeDisplayDriverDx10_Functions_48ca8f95-06ba-4a11-8517-bd4638691e65.xml, d3d10umddi/CalcPrivateRenderTargetViewSize, display.calcprivaterendertargetviewsize
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/CalcPrivateRenderTargetViewSize"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateRenderTargetViewSize
product:
 - Windows
---

# PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE callback function

## -description

The <b>CalcPrivateRenderTargetViewSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a render target view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateRenderTargetView* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createrendertargetview">D3D10DDIARG_CREATERENDERTARGETVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateRenderTargetViewSize</b> returns the size of the memory region that the driver requires for creating a render target view.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createrendertargetview">D3D10DDIARG_CREATERENDERTARGETVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>

