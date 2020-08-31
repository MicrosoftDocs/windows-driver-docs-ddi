---
UID: NC:d3d10umddi.PFND3D10DDI_DRAW
title: PFND3D10DDI_DRAW (d3d10umddi.h)
description: The Draw function draws nonindexed primitives.
old-location: display\draw.htm
ms.assetid: 7a6f1d56-12be-4185-97bf-06f265ee6fe3
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_DRAW callback function"]
ms.keywords: Draw, Draw callback function [Display Devices], PFND3D10DDI_DRAW, PFND3D10DDI_DRAW callback, UserModeDisplayDriverDx10_Functions_aec9f82d-41e9-41bc-b8e7-c07c531caf4c.xml, d3d10umddi/Draw, display.draw
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
 - PFND3D10DDI_DRAW
 - d3d10umddi/PFND3D10DDI_DRAW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - Draw
---

# PFND3D10DDI_DRAW callback function


## -description

The <b>Draw</b> function draws nonindexed primitives.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*VertexCount* [in]

The number of vertices in the vertex buffer that vertices are read from to draw the primitives.

### -param Arg3

*StartVertexLocation* [in]

The first vertex in the vertex buffer that vertices are read from to draw the primitives.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>Draw</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

