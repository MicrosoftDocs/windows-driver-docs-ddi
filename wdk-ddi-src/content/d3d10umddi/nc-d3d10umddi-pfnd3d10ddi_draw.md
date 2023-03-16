---
UID: NC:d3d10umddi.PFND3D10DDI_DRAW
title: PFND3D10DDI_DRAW (d3d10umddi.h)
description: Learn more about the pfnDraw function.
ms.date: 03/15/2023
keywords: ["PFND3D10DDI_DRAW callback function"]
ms.keywords: Draw, Draw callback function [Display Devices], PFND3D10DDI_DRAW, PFND3D10DDI_DRAW callback, UserModeDisplayDriverDx10_Functions_aec9f82d-41e9-41bc-b8e7-c07c531caf4c.xml, d3d10umddi/Draw, display.draw
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - PFND3D10DDI_DRAW
---

# PFND3D10DDI_DRAW callback function

## -description

The **pfnDraw** function draws non-indexed primitives.

## -parameters

### -param unnamedParam1

[in] **hDevice**: A handle to the display device (graphics context).

### -param unnamedParam2

[in] **VertexCount**: The number of vertices in the vertex buffer that vertices are read from to draw the primitives.

### -param unnamedParam3

[in] **StartVertexLocation**: The first vertex in the vertex buffer that vertices are read from to draw the primitives.

## -remarks

The driver can use the [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) callback function to set an error code.

The only error a driver should encounter is D3DDDIERR_DEVICEREMOVED. If the driver passes a different error to **pfnSetErrorCb**, the Direct3D runtime will determine that the error is critical.

Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED. However, if device removal interfered with the **pfnDraw** operation (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

[**D3D10DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10ddi_devicefuncs.md)

[**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md)
