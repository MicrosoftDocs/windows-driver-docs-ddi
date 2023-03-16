---
UID: NC:d3d10umddi.PFND3D10DDI_DRAWINDEXED
title: PFND3D10DDI_DRAWINDEXED (d3d10umddi.h)
description: Learn more about the PFND3D10DDI_DRAWINDEXED callback function draws indexed primitives.
ms.date: 03/15/2023
keywords: ["PFND3D10DDI_DRAWINDEXED callback function"]
ms.keywords: DrawIndexed, DrawIndexed callback function [Display Devices], PFND3D10DDI_DRAWINDEXED, PFND3D10DDI_DRAWINDEXED callback, UserModeDisplayDriverDx10_Functions_4529cc06-0ad4-41ea-8cab-b55a398cb889.xml, d3d10umddi/DrawIndexed, display.drawindexed
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
 - PFND3D10DDI_DRAWINDEXED
 - d3d10umddi/PFND3D10DDI_DRAWINDEXED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_DRAWINDEXED
---

# PFND3D10DDI_DRAWINDEXED callback function

## -description

The **pfnDrawIndexed** function draws indexed primitives.

## -parameters

### -param unnamedParam1

[in] **hDevice**: A handle to the display device (graphics context).

### -param unnamedParam2

[in] **IndexCount**: The number of indices in the index buffer that identify the vertex buffer vertices to draw.

### -param unnamedParam3

[in] **StartIndexLocation**: The location of the first index to read from the index buffer.

### -param unnamedParam4

[in] **BaseVertexLocation**: The value added to each index before reading a vertex from the vertex buffer.

## -remarks

For an example on how to use indices and vertices, see [Understand the Direct3D 11 rendering pipeline](/windows/win32/direct3dgetstarted/understand-the-directx-11-2-graphics-pipeline).

The driver can use the [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) callback function to set an error code.

The only error a driver should encounter is D3DDDIERR_DEVICEREMOVED. If the driver passes a different error to **pfnSetErrorCb**, the Direct3D runtime will determine that the error is critical.

Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED. However, if device removal interfered with the **pfnDrawIndexed** operation (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

[**D3D10DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10ddi_devicefuncs.md)

[**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md)
