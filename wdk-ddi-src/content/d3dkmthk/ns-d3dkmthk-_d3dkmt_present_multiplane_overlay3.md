---
UID: NS:d3dkmthk._D3DKMT_PRESENT_MULTIPLANE_OVERLAY3
title: _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 (d3dkmthk.h)
description: Contains present multiplane overlay information.
ms.date: 10/19/2018
keywords: ["D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 structure"]
ms.keywords: _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3, D3DKMT_PRESENT_MULTIPLANE_OVERLAY3,
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
req.typenames: D3DKMT_PRESENT_MULTIPLANE_OVERLAY3
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3
 - d3dkmthk/_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3
 - D3DKMT_PRESENT_MULTIPLANE_OVERLAY3
 - d3dkmthk/D3DKMT_PRESENT_MULTIPLANE_OVERLAY3
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3
dev_langs:
 - c++
---

# _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 structure


## -description

Contains present multiplane overlay information.

## -struct-fields

### -field hAdapter

A handle to the graphics adapter.

### -field ContextCount

The context count.

### -field pContextList

Pointer to a context list.

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field PresentCount

The number of present operations that can be queued for the device that is specified by *hDevice*.

### -field Flags

### -field PresentPlaneCount

The number of resources to pin.

### -field ppPresentPlanes

Pointer to an array of present planes.

### -field pPostComposition

Pointer to post composition.

### -field Duration

Per-present duration.

### -field HDRMetaDataType

The HDR metadata type.

### -field HDRMetaDataSize

The HDR metadata size.

### -field pHDRMetaData

 
The HDR metadata.

## -remarks

## -see-also

