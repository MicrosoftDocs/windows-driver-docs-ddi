---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE
title: PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE (d3d10umddi.h)
description: The CalcPrivateDeferredContextSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a deferred context.
old-location: display\calcprivatedeferredcontextsize.htm
ms.assetid: 282898b1-45e1-4d85-9ab7-fd400623bdc5
ms.date: 05/10/2018
ms.keywords: CalcPrivateDeferredContextSize, CalcPrivateDeferredContextSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE, PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE callback, UserModeDisplayDriverDx11_Functions_577f34a4-1f2e-4666-8bce-00dc6e52c2e6.xml, d3d10umddi/CalcPrivateDeferredContextSize, display.calcprivatedeferredcontextsize
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateDeferredContextSize is supported beginning with the Windows 7 operating system.
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
 - "d3d10umddi/CalcPrivateDeferredContextSize"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateDeferredContextSize
product:
 - Windows
---

# PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE callback function

## -description

The <b>CalcPrivateDeferredContextSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a deferred context.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCalcPrivateDeferredContextSize* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_calcprivatedeferredcontextsize">D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateDeferredContextSize</b> returns the size of the memory region that the driver requires to create a deferred context.

## -remarks

The driver is only required to implement <b>CalcPrivateDeferredContextSize</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_calcprivatedeferredcontextsize">D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>

