---
UID: NS:d3dumddi._D3DDDIARG_CREATEOVERLAY
title: _D3DDDIARG_CREATEOVERLAY (d3dumddi.h)
description: The D3DDDIARG_CREATEOVERLAY structure describes an overlay to create.
old-location: display\d3dddiarg_createoverlay.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_CREATEOVERLAY structure"]
ms.keywords: D3DDDIARG_CREATEOVERLAY, D3DDDIARG_CREATEOVERLAY structure [Display Devices], UMDisplayDriver_param_Structs_3261a00d-4b26-4c64-a5e0-abd453aee84c.xml, _D3DDDIARG_CREATEOVERLAY, d3dumddi/D3DDDIARG_CREATEOVERLAY, display.d3dddiarg_createoverlay
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: D3DDDIARG_CREATEOVERLAY
f1_keywords:
 - _D3DDDIARG_CREATEOVERLAY
 - d3dumddi/_D3DDDIARG_CREATEOVERLAY
 - D3DDDIARG_CREATEOVERLAY
 - d3dumddi/D3DDDIARG_CREATEOVERLAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_CREATEOVERLAY
---

# _D3DDDIARG_CREATEOVERLAY structure


## -description

The D3DDDIARG_CREATEOVERLAY structure describes an overlay to create.

## -struct-fields

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to overlay on (that is, the identifier of the primary surface to overlay on).

### -field OverlayInfo

[in] A pointer to the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlayinfo">D3DDDI_OVERLAYINFO</a> structure that describes information about the overlay.

### -field hOverlay

[out] A handle to the overlay. The user-mode display driver must set this handle to a value that the Microsoft Direct3D runtime can use to identify the overlay hardware in subsequent calls.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlay">CreateOverlay</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlayinfo">D3DDDI_OVERLAYINFO</a>
