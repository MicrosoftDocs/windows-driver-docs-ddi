---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_SOURCE_MODE
title: D3DKMDT_VIDPN_SOURCE_MODE (d3dkmdt.h)
description: The D3DKMDT_VIDPN_SOURCE_MODE structure contains information about a video present network (VidPN) source mode.
old-location: display\d3dkmdt_vidpn_source_mode.htm
tech.root: display
ms.date: 05/24/2022
keywords: ["D3DKMDT_VIDPN_SOURCE_MODE structure"]
ms.keywords: D3DKMDT_VIDPN_SOURCE_MODE, D3DKMDT_VIDPN_SOURCE_MODE structure [Display Devices], DmStructs_0e8655c2-a85f-411d-a791-4c85e5c7d52c.xml, _D3DKMDT_VIDPN_SOURCE_MODE, d3dkmdt/D3DKMDT_VIDPN_SOURCE_MODE, display.d3dkmdt_vidpn_source_mode
req.header: d3dkmdt.h
req.include-header: 
req.target-type: Windows
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
req.typenames: D3DKMDT_VIDPN_SOURCE_MODE
f1_keywords:
 - _D3DKMDT_VIDPN_SOURCE_MODE
 - d3dkmdt/_D3DKMDT_VIDPN_SOURCE_MODE
 - D3DKMDT_VIDPN_SOURCE_MODE
 - d3dkmdt/D3DKMDT_VIDPN_SOURCE_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMDT_VIDPN_SOURCE_MODE
 - D3DKMDT_VIDPN_SOURCE_MODE
---

# D3DKMDT_VIDPN_SOURCE_MODE structure

## -description

The **D3DKMDT_VIDPN_SOURCE_MODE** structure contains information about a video present network (VidPN) source mode.

## -struct-fields

### -field Id

An integer that identifies the source mode. The identifier is generated and filled in by the VidPN manager. However, the display miniport driver has the option of overwriting the identifier. For more information, see [**pfnCreateNewModeInfo**](../d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo.md).

### -field Type

A [**D3DKMDT_VIDPN_SOURCE_MODE_TYPE**](ne-d3dkmdt-_d3dkmdt_vidpn_source_mode_type.md) enumerator that indicates the mode type: graphics or text.

### -field Format

A union that contains information about either the graphics rendering format or the text format in the following members.

### -field Format.Graphics

A [**D3DKMDT_GRAPHICS_RENDERING_FORMAT**](ns-d3dkmdt-_d3dkmdt_graphics_rendering_format.md) structure that contains information about the graphics rendering format (for example, primary surface size and pixel format). This member is meaningful only if the **Type** member is equal to D3DKMDT_RMT_GRAPHICS.

### -field Format.Text

A [**D3DKMDT_TEXT_RENDERING_FORMAT**](ne-d3dkmdt-_d3dkmdt_text_rendering_format.md) enumerator that indicates the text format. This member is meaningful only if the **Type** member is equal to D3DKMDT_RMT_TEXT.

## -remarks

For more information about video present sources and VidPN source modes, see [Introduction to Video Present Networks](/windows-hardware/drivers/display/introduction-to-video-present-networks) and [Enumerating Cofunctional VidPN Source and Target Modes](/windows-hardware/drivers/display/enumerating-cofunctional-vidpn-source-and-target-modes).

## -see-also

[**D3DKMDT_MONITOR_SOURCE_MODE**](ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md)

[**D3DKMDT_VIDPN_TARGET_MODE**](ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md)
