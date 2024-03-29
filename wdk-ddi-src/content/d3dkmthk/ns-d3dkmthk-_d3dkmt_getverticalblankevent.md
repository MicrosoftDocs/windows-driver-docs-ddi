---
UID: NS:d3dkmthk._D3DKMT_GETVERTICALBLANKEVENT
title: _D3DKMT_GETVERTICALBLANKEVENT (d3dkmthk.h)
description: Used to get vertical blank events.
ms.date: 10/19/2018
keywords: ["D3DKMT_GETVERTICALBLANKEVENT structure"]
ms.keywords: _D3DKMT_GETVERTICALBLANKEVENT, D3DKMT_GETVERTICALBLANKEVENT,
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
req.typenames: D3DKMT_GETVERTICALBLANKEVENT
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_GETVERTICALBLANKEVENT
 - d3dkmthk/_D3DKMT_GETVERTICALBLANKEVENT
 - D3DKMT_GETVERTICALBLANKEVENT
 - d3dkmthk/D3DKMT_GETVERTICALBLANKEVENT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_GETVERTICALBLANKEVENT
 - D3DKMT_GETVERTICALBLANKEVENT
dev_langs:
 - c++
---

# _D3DKMT_GETVERTICALBLANKEVENT structure


## -description

Used to get vertical blank events.

## -struct-fields

### -field hAdapter [in]

A handle to the graphics adapter.

### -field hDevice [in]

A handle to the device.

### -field VidPnSourceId [in]

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field phEvent [in, out]

 
Pointer to an event handle.

## -remarks

## -see-also

