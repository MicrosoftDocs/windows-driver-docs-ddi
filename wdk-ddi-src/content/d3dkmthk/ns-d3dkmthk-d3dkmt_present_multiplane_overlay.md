---
UID: NS:d3dkmthk.D3DKMT_PRESENT_MULTIPLANE_OVERLAY
title: D3DKMT_PRESENT_MULTIPLANE_OVERLAY (d3dkmthk.h)
description: Contains present multiplane overlay information.
ms.assetid: 4f98ff62-0189-452e-82cc-dbd596aa7a48
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3DKMT_PRESENT_MULTIPLANE_OVERLAY, D3DKMT_PRESENT_MULTIPLANE_OVERLAY, 
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
req.typenames: D3DKMT_PRESENT_MULTIPLANE_OVERLAY
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- D3DKMT_PRESENT_MULTIPLANE_OVERLAY
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# D3DKMT_PRESENT_MULTIPLANE_OVERLAY structure

## -description

Contains present multiplane overlay information.

## -struct-fields

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
