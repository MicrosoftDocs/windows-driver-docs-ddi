---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATERESOURCESIZE
title: PFND3D11DDI_CALCPRIVATERESOURCESIZE (d3d10umddi.h)
description: The CalcPrivateResourceSize(D3D11) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory).
old-location: display\calcprivateresourcesize_d3d11_.htm
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_CALCPRIVATERESOURCESIZE callback function"]
ms.keywords: CalcPrivateResourceSize, CalcPrivateResourceSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATERESOURCESIZE, PFND3D11DDI_CALCPRIVATERESOURCESIZE callback, UserModeDisplayDriverDx11_Functions_85fd70d1-91ec-4b9d-b379-18b5d3d43e67.xml, d3d10umddi/CalcPrivateResourceSize, display.calcprivateresourcesize_d3d11_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateResourceSize(D3D11) is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_CALCPRIVATERESOURCESIZE
 - d3d10umddi/PFND3D11DDI_CALCPRIVATERESOURCESIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateResourceSize
product:
 - Windows
---

# PFND3D11DDI_CALCPRIVATERESOURCESIZE callback function


## -description

The <b>CalcPrivateResourceSize(D3D11)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory).

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateResource* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateResourceSize(D3D11)</b> returns the size of the memory region that the driver requires to create resources.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>
