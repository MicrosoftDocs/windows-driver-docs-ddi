---
UID: NS:d3dumddi._D3DDDIARG_UPDATEOVERLAY
title: _D3DDDIARG_UPDATEOVERLAY (d3dumddi.h)
description: The D3DDDIARG_UPDATEOVERLAY structure describes an overlay to modify.
old-location: display\d3dddiarg_updateoverlay.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_UPDATEOVERLAY structure"]
ms.keywords: D3DDDIARG_UPDATEOVERLAY, D3DDDIARG_UPDATEOVERLAY structure [Display Devices], UMDisplayDriver_param_Structs_6c415566-a5f5-4efc-820b-7eb466b59149.xml, _D3DDDIARG_UPDATEOVERLAY, d3dumddi/D3DDDIARG_UPDATEOVERLAY, display.d3dddiarg_updateoverlay
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
req.typenames: D3DDDIARG_UPDATEOVERLAY
f1_keywords:
 - _D3DDDIARG_UPDATEOVERLAY
 - d3dumddi/_D3DDDIARG_UPDATEOVERLAY
 - D3DDDIARG_UPDATEOVERLAY
 - d3dumddi/D3DDDIARG_UPDATEOVERLAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_UPDATEOVERLAY
---

# _D3DDDIARG_UPDATEOVERLAY structure


## -description

The D3DDDIARG_UPDATEOVERLAY structure describes an overlay to modify.

## -struct-fields

### -field hOverlay

[in] A handle to the overlay to modify.

### -field OverlayInfo

[in] A pointer to the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlayinfo">D3DDDI_OVERLAYINFO</a> structure that describes the modification for the overlay.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlayinfo">D3DDDI_OVERLAYINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_updateoverlay">UpdateOverlay</a>
