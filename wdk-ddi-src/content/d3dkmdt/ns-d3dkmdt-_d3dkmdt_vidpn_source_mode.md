---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_SOURCE_MODE
title: _D3DKMDT_VIDPN_SOURCE_MODE (d3dkmdt.h)
description: The D3DKMDT_VIDPN_SOURCE_MODE structure contains information about a video present network (VidPN) source mode.
old-location: display\d3dkmdt_vidpn_source_mode.htm
tech.root: display
ms.assetid: 763db6bb-8991-406d-a1d4-8ad50e32fee1
ms.date: 05/10/2018
ms.keywords: D3DKMDT_VIDPN_SOURCE_MODE, D3DKMDT_VIDPN_SOURCE_MODE structure [Display Devices], DmStructs_0e8655c2-a85f-411d-a791-4c85e5c7d52c.xml, _D3DKMDT_VIDPN_SOURCE_MODE, d3dkmdt/D3DKMDT_VIDPN_SOURCE_MODE, display.d3dkmdt_vidpn_source_mode
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
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
req.typenames: D3DKMDT_VIDPN_SOURCE_MODE
f1_keywords:
 - "d3dkmdt/D3DKMDT_VIDPN_SOURCE_MODE"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - D3DKMDT_VIDPN_SOURCE_MODE
product:
 - Windows
---

# _D3DKMDT_VIDPN_SOURCE_MODE structure

## -description

The D3DKMDT_VIDPN_SOURCE_MODE structure contains information about a video present network (VidPN) source mode.

## -struct-fields

### -field Id

An integer that identifies the source mode. The identifier is generated and filled in by the VidPN manager. However, the display miniport driver has the option of overwriting the identifier. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo">pfnCreateNewModeInfo</a>.

### -field Type

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_vidpn_source_mode_type">D3DKMDT_VIDPN_SOURCE_MODE_TYPE</a> enumerator that indicates the mode type: graphics or text.

### -field Format

A union that contains information about either the graphics rendering format or the text format in the following members.

### -field Graphics

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_graphics_rendering_format">D3DKMDT_GRAPHICS_RENDERING_FORMAT</a> structure that contains information about the graphics rendering format (for example, primary surface size and pixel format). This member is meaningful only if the <b>Type</b> member is equal to D3DKMDT_RMT_GRAPHICS.

### -field Text

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_text_rendering_format">D3DKMDT_TEXT_RENDERING_FORMAT</a> enumerator that indicates the text format. This member is meaningful only if the <b>Type</b> member is equal to D3DKMDT_RMT_TEXT.

## -remarks

For more information about video present sources and VidPN source modes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/introduction-to-video-present-networks">Introduction to Video Present Networks</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/display/enumerating-cofunctional-vidpn-source-and-target-modes">Enumerating Cofunctional VidPN Source and Target Modes</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">VidPN Source Mode Set Interface</a>

