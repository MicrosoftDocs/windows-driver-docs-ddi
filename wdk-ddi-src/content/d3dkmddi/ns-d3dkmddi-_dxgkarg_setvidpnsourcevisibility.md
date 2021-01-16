---
UID: NS:d3dkmddi._DXGKARG_SETVIDPNSOURCEVISIBILITY
title: _DXGKARG_SETVIDPNSOURCEVISIBILITY (d3dkmddi.h)
description: The DXGKARG_SETVIDPNSOURCEVISIBILITY structure contains arguments for the DxgkDdiSetVidPnSourceVisibility function.
old-location: display\dxgkarg_setvidpnsourcevisibility.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_SETVIDPNSOURCEVISIBILITY structure"]
ms.keywords: DXGKARG_SETVIDPNSOURCEVISIBILITY, DXGKARG_SETVIDPNSOURCEVISIBILITY structure [Display Devices], DmStructs_877a0a99-de1a-4f16-81af-e9dae624281a.xml, _DXGKARG_SETVIDPNSOURCEVISIBILITY, d3dkmddi/DXGKARG_SETVIDPNSOURCEVISIBILITY, display.dxgkarg_setvidpnsourcevisibility
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
tech.root: display
req.typenames: DXGKARG_SETVIDPNSOURCEVISIBILITY
f1_keywords:
 - _DXGKARG_SETVIDPNSOURCEVISIBILITY
 - d3dkmddi/_DXGKARG_SETVIDPNSOURCEVISIBILITY
 - DXGKARG_SETVIDPNSOURCEVISIBILITY
 - d3dkmddi/DXGKARG_SETVIDPNSOURCEVISIBILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETVIDPNSOURCEVISIBILITY
 - DXGKARG_SETVIDPNSOURCEVISIBILITY
---

# _DXGKARG_SETVIDPNSOURCEVISIBILITY structure


## -description

The DXGKARG_SETVIDPNSOURCEVISIBILITY structure contains arguments for the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourcevisibility">DxgkDdiSetVidPnSourceVisibility</a> function.

## -struct-fields

### -field VidPnSourceId

An integer that identifies a video present source on the display adapter.

### -field Visible

A Boolean value that specifies whether the video output codec associated with the source must start scanning or stop scanning the source's primary surface. If <b>Visible</b> is <b>TRUE</b>, the codec must start scanning. 

If <b>Visible</b> is <b>FALSE</b>, the codec must stop scanning. However, a VSync signal should be generated even if a call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourcevisibility">DxgkDdiSetVidPnSourceVisibility</a> function sets <b>Visible</b> to <b>FALSE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourcevisibility">DxgkDdiSetVidPnSourceVisibility</a>

