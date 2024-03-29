---
UID: NS:d3dkmthk._D3DKMT_PRESENT_MULTIPLANE_OVERLAY2
title: _D3DKMT_PRESENT_MULTIPLANE_OVERLAY2 (d3dkmthk.h)
description: The _D3DKMT_PRESENT_MULTIPLANE_OVERLAY2 structure contains information about the present multiplane overlay.
ms.date: 10/19/2018
keywords: ["D3DKMT_PRESENT_MULTIPLANE_OVERLAY2 structure"]
ms.keywords: _D3DKMT_PRESENT_MULTIPLANE_OVERLAY2, D3DKMT_PRESENT_MULTIPLANE_OVERLAY2,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_PRESENT_MULTIPLANE_OVERLAY2
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_PRESENT_MULTIPLANE_OVERLAY2
 - d3dkmthk/_D3DKMT_PRESENT_MULTIPLANE_OVERLAY2
 - D3DKMT_PRESENT_MULTIPLANE_OVERLAY2
 - d3dkmthk/D3DKMT_PRESENT_MULTIPLANE_OVERLAY2
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_PRESENT_MULTIPLANE_OVERLAY2
 - D3DKMT_PRESENT_MULTIPLANE_OVERLAY2
dev_langs:
 - c++
---

# _D3DKMT_PRESENT_MULTIPLANE_OVERLAY2 structure


## -description

Contains present multiplane overlay information.

## -struct-fields

### -field hAdapter

A handle to the graphics adapter.

### -field hDevice

A handle to the device.

### -field hContext

A handle to the device context.

### -field BroadcastContextCount

Specifies the number of contexts.

### -field BroadcastContext

A D3DKMT_HANDLE data type that represents the broadcast context.

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field PresentCount

The number of present operations that can be queued for the device that is specified by *hDevice*.

### -field FlipInterval

A UINT value that specifies whether the display miniport driver natively supports the scheduling of a flip command to take effect after two, three or four vertical syncs occur.

### -field Flags

Flag options.

### -field PresentPlaneCount

The number of resources to pin.

### -field pPresentPlanes

Pointer to present planes.

### -field Duration

 
Per-present duration.

## -remarks

## -see-also

