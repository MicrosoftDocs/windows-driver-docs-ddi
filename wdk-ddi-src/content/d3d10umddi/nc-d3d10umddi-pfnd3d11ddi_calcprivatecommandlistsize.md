---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE
title: PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE (d3d10umddi.h)
description: The CalcPrivateCommandListSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a command list.
old-location: display\calcprivatecommandlistsize.htm
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE callback function"]
ms.keywords: CalcPrivateCommandListSize, CalcPrivateCommandListSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE, PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE callback, UserModeDisplayDriverDx11_Functions_ba8c13ec-47a3-4d4a-9356-59c9a3edd34d.xml, d3d10umddi/CalcPrivateCommandListSize, display.calcprivatecommandlistsize
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateCommandListSize is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE
 - d3d10umddi/PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE
product:
 - Windows
---

# PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE callback function


## -description

The <b>CalcPrivateCommandListSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a command list.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateCommandList* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createcommandlist">D3D11DDIARG_CREATECOMMANDLIST</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateCommandListSize</b> returns the size of the memory region that the driver requires to create a command list.

## -remarks

The driver is only required to implement <b>CalcPrivateCommandListSize</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createcommandlist">D3D11DDIARG_CREATECOMMANDLIST</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>

