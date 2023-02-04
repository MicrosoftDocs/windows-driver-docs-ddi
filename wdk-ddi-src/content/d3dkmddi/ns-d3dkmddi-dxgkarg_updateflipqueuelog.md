---
UID: NS:d3dkmddi._DXGKARG_UPDATEFLIPQUEUELOG
tech.root: display
title: DXGKARG_UPDATEFLIPQUEUELOG
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGKARG_UPDATEFLIPQUEUELOG structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_UPDATEFLIPQUEUELOG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_UPDATEFLIPQUEUELOG
 - DXGKARG_UPDATEFLIPQUEUELOG
f1_keywords:
 - _DXGKARG_UPDATEFLIPQUEUELOG
 - d3dkmddi/_DXGKARG_UPDATEFLIPQUEUELOG
 - DXGKARG_UPDATEFLIPQUEUELOG
 - d3dkmddi/DXGKARG_UPDATEFLIPQUEUELOG
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_UPDATEFLIPQUEUELOG
---

## -description

The **DXGKARG_UPDATEFLIPQUEUELOG** structure contains parameters for the driver's [**DXGKDDI_UPDATEFLIPQUEUELOG**](nc-d3dkmddi-dxgkddi_updateflipqueuelog.md) callback function.

## -struct-fields

### -field VidPnSourceId

[in] [in] A **D3DDDI_VIDEO_PRESENT_SOURCE_ID** value that identifies the VidPn source ID of the hardware flip queue.

### -field LayerIndex

[in] A zero-based index value that identifies the MPO plane index of the flip queue.

### -field FirstFreeFlipQueueLogEntryIndex

[out] Location in which the driver returns the index after the last written entry in the flip queue log buffer.

## -remarks

See [Hardware flip queue](/windows-hardware/drivers/display/hardware-flip-queue) for more information.

## -see-also

[**DXGKDDI_UPDATEFLIPQUEUELOG**](nc-d3dkmddi-dxgkddi_updateflipqueuelog.md)
