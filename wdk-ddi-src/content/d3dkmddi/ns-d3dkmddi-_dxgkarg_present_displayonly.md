---
UID: NS:d3dkmddi._DXGKARG_PRESENT_DISPLAYONLY
title: _DXGKARG_PRESENT_DISPLAYONLY (d3dkmddi.h)
description: Indicates how a kernel mode display-only driver (KMDOD) is to perform a present operation.
old-location: display\dxgkarg_present_displayonly.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_PRESENT_DISPLAYONLY structure"]
ms.keywords: DXGKARG_PRESENT_DISPLAYONLY, DXGKARG_PRESENT_DISPLAYONLY structure [Display Devices], _DXGKARG_PRESENT_DISPLAYONLY, d3dkmddi/DXGKARG_PRESENT_DISPLAYONLY, display.dxgkarg_present_displayonly
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: DXGKARG_PRESENT_DISPLAYONLY
f1_keywords:
 - _DXGKARG_PRESENT_DISPLAYONLY
 - d3dkmddi/_DXGKARG_PRESENT_DISPLAYONLY
 - DXGKARG_PRESENT_DISPLAYONLY
 - d3dkmddi/DXGKARG_PRESENT_DISPLAYONLY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - _DXGKARG_PRESENT_DISPLAYONLY
 - DXGKARG_PRESENT_DISPLAYONLY
---

# _DXGKARG_PRESENT_DISPLAYONLY structure


## -description

Indicates how a kernel mode display-only driver (KMDOD) is to perform a present operation.

## -struct-fields

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology on which to restrict displaying.

### -field pSource

The virtual start address of the source image.

### -field BytesPerPixel

The number of bytes per pixel in the source image.

### -field Pitch

The pitch, in bytes, of each line in the source image—that is, the distance, in bytes, to the start of the next line.

### -field Flags

A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_d3dkmt_present_display_only_flags">D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS</a> structure that identifies how to display the source image in the present operation.

### -field NumMoves

The number of screen-to-screen moves that are pointed to by the <b>pMoves</b> member.

### -field pMoves

A pointer to a list of <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmt_move_rect">D3DKMT_MOVE_RECT</a> screen-to-screen moves.

### -field NumDirtyRects

The number of dirty rectangles that are pointed to by the <b>pDirtyRect</b> member.

### -field pDirtyRect

A pointer to a list of <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> dirty rectangles.

### -field pfnPresentDisplayOnlyProgress

Reserved for system use. The operating system sets this member to <b>NULL</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmt_move_rect">D3DKMT_MOVE_RECT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_d3dkmt_present_display_only_flags">D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS</a>



<a href="/windows-hardware/drivers/display/dxgkcbpresentdisplayonlyprogress">DxgkCbPresentDisplayOnlyProgress</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_presentdisplayonly">DxgkDdiPresentDisplayOnly</a>



<a href="/windows/win32/api/windef/ns-windef-rect">RECT</a>

