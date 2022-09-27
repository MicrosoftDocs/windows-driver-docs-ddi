---
UID: NS:d3dkmddi._DXGK_RENDERKM_COMMAND
title: DXGK_RENDERKM_COMMAND (d3dkmddi.h)
description: The DXGK_RENDERKM_COMMAND structure is used to construct a command buffer to control GDI hardware-accelerated rendering.
old-location: display\dxgk_renderkm_command.htm
ms.date: 08/24/2022
keywords: ["DXGK_RENDERKM_COMMAND structure"]
ms.keywords: DXGK_RENDERKM_COMMAND, DXGK_RENDERKM_COMMAND structure [Display Devices], DmStructs_b23578a5-ae81-42c8-95ce-3ba9b4691d57.xml, _DXGK_RENDERKM_COMMAND, d3dkmddi/DXGK_RENDERKM_COMMAND, display.dxgk_renderkm_command
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.typenames: DXGK_RENDERKM_COMMAND
f1_keywords:
 - _DXGK_RENDERKM_COMMAND
 - d3dkmddi/_DXGK_RENDERKM_COMMAND
 - DXGK_RENDERKM_COMMAND
 - d3dkmddi/DXGK_RENDERKM_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_RENDERKM_COMMAND
 - DXGK_RENDERKM_COMMAND
product:
 - Windows
---

# DXGK_RENDERKM_COMMAND structure

## -description

The **DXGK_RENDERKM_COMMAND** structure is used to construct a command buffer to control GDI hardware-accelerated rendering.

## -struct-fields

### -field OpCode

[in] A [**DXGK_RENDERKM_OPERATION**](ne-d3dkmddi-_dxgk_renderkm_operation.md)-type operation code that identifies the GDI hardware-accelerated rendering operation to process. For more information about GDI hardware acceleration, see the Remarks section.

### -field CommandSize

[in] The size of the current command, in bytes. This is equal to the number of bytes from the beginning of DXGK_RENDERKM_COMMAND up to the next command.

### -field Command

The command.

### -field Command.BitBlt

[in] A bit-block transfer (bitblt) that is described by a [**DXGK_GDIARG_BITBLT**](ns-d3dkmddi-_dxgk_gdiarg_bitblt.md) structure.

### -field Command.ColorFill

[in] A color fill that is described by a [**DXGK_GDIARG_COLORFILL**](ns-d3dkmddi-_dxgk_gdiarg_colorfill.md) structure.

### -field Command.AlphaBlend

[in] An alpha blend that is described by a [**DXGK_GDIARG_ALPHABLEND**](ns-d3dkmddi-_dxgk_gdiarg_alphablend.md) structure.

### -field Command.StretchBlt

[in] A stretch bit-block transfer that is described by a [**DXGK_GDIARG_STRETCHBLT**](ns-d3dkmddi-_dxgk_gdiarg_stretchblt.md) structure.

### -field Command.TransparentBlt

[in] A transparent bit-block transfer that is described by a [**DXGK_GDIARG_TRANSPARENTBLT**](ns-d3dkmddi-_dxgk_gdiarg_transparentblt.md) structure.

### -field Command.ClearTypeBlend

[in] A ClearType blend that is described by a [**DXGK_GDIARG_CLEARTYPEBLEND**](ns-d3dkmddi-_dxgk_gdiarg_cleartypeblend.md) structure.

## -remarks

An array of variable-size DXGK_RENDERKM_COMMAND structures defines a command buffer that is used to control GDI hardware-accelerated rendering.

A display miniport driver should report that it supports command buffer processing for GDI hardware acceleration by setting [**DXGK_DRIVERCAPS**](ns-d3dkmddi-_dxgk_drivercaps.md)->**PresentationCaps**.**SupportKernelModeCommandBuffer** to TRUE.

> [!NOTE]
> A display miniport driver should report that it supports GDI hardware acceleration only if the cache-coherent GPU aperture segment exists, and there is no significant performance penalty when the CPU accesses the memory.

Each command varies in length depending on the value of the **OpCode** member and the number of sub-rectangles in the command.

## -see-also

[**DXGK_DRIVERCAPS**](ns-d3dkmddi-_dxgk_drivercaps.md)

[**DXGK_GDIARG_ALPHABLEND**](ns-d3dkmddi-_dxgk_gdiarg_alphablend.md)

[**DXGK_GDIARG_BITBLT**](ns-d3dkmddi-_dxgk_gdiarg_bitblt.md)

[**DXGK_GDIARG_CLEARTYPEBLEND**](ns-d3dkmddi-_dxgk_gdiarg_cleartypeblend.md)

[**DXGK_GDIARG_COLORFILL**](ns-d3dkmddi-_dxgk_gdiarg_colorfill.md)

[**DXGK_GDIARG_STRETCHBLT**](ns-d3dkmddi-_dxgk_gdiarg_stretchblt.md)

[**DXGK_GDIARG_TRANSPARENTBLT**](ns-d3dkmddi-_dxgk_gdiarg_transparentblt.md)

[**DXGK_PRESENTATIONCAPS**](ns-d3dkmddi-_dxgk_presentationcaps.md)

[**DXGK_RENDERKM_OPERATION**](ne-d3dkmddi-_dxgk_renderkm_operation.md)
