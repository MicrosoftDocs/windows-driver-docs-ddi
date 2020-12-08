---
UID: NE:d3dkmddi._DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
title: _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON (d3dkmddi.h)
description: The DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration is used to indicate the reason why an active VidPN is invalidated and a new VidPN is requested.
old-location: display\dxgk_active_vidpn_invalidation_reason.htm
ms.date: 05/10/2018
keywords: ["DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration"]
ms.keywords: DXGK_ACTIVE_VIDPN_INVALIDATION_REASON, DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration [Display Devices], DXGK_AVIR_HOTKEY, DXGK_AVIR_UNINITIALIZED, DXGK_AVIR_USERMODE, DmEnums_9a263431-3cae-4e33-a2f0-310ec88c1343.xml, _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON, d3dkmddi/DXGK_ACTIVE_VIDPN_INVALIDATION_REASON, d3dkmddi/DXGK_AVIR_HOTKEY, d3dkmddi/DXGK_AVIR_UNINITIALIZED, d3dkmddi/DXGK_AVIR_USERMODE, display.dxgk_active_vidpn_invalidation_reason
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
req.typenames: DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
f1_keywords:
 - _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
 - d3dkmddi/_DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
 - DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
 - d3dkmddi/DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
---

# _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration


## -description

The DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration is used to indicate the reason why an active VidPN is invalidated and a new VidPN is requested.

## -enum-fields

### -field DXGK_AVIR_UNINITIALIZED

Indicates that a variable of type DXGK_ACTIVE_VIDPN_INVALIDATION_REASON has not yet been assigned a meaningful value.

### -field DXGK_AVIR_HOTKEY

Indicates that the user pressed a keyboard shortcut to change the set of monitors (or other display devices) being used to display the desktop.

### -field DXGK_AVIR_USERMODE

Indicates that a call to the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtinvalidateactivevidpn">D3DKMTInvalidateActiveVidPn</a> function has been made in user mode.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtinvalidateactivevidpn">D3DKMTInvalidateActiveVidPN</a>
