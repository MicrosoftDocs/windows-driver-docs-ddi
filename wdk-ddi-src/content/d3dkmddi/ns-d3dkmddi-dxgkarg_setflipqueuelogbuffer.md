---
UID: NS:d3dkmddi._DXGKARG_SETFLIPQUEUELOGBUFFER
tech.root: display
title: DXGKARG_SETFLIPQUEUELOGBUFFER
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGKARG_SETFLIPQUEUELOGBUFFER structure.
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
req.typenames: DXGKARG_SETFLIPQUEUELOGBUFFER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETFLIPQUEUELOGBUFFER
 - DXGKARG_SETFLIPQUEUELOGBUFFER
f1_keywords:
 - _DXGKARG_SETFLIPQUEUELOGBUFFER
 - d3dkmddi/_DXGKARG_SETFLIPQUEUELOGBUFFER
 - DXGKARG_SETFLIPQUEUELOGBUFFER
 - d3dkmddi/DXGKARG_SETFLIPQUEUELOGBUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_SETFLIPQUEUELOGBUFFER
---

## -description

The **DXGKARG_SETFLIPQUEUELOGBUFFER** structure contains parameters for the driver's [**DXGKDDI_SETFLIPQUEUELOGBUFFER**](nc-d3dkmddi-dxgkddi_setflipqueuelogbuffer.md) callback function.

## -struct-fields

### -field VidPnSourceId

[in] A **D3DDDI_VIDEO_PRESENT_SOURCE_ID** value that identifies the VidPn source ID for which the flip queue log buffer is being provided.

### -field LayerIndex

[in] A zero-based index value that identifies the MPO plane index for which the flip queue log buffer is being provided.

### -field NumberOfEntries

[in] The number of entries in the flip queue log buffer that **LogBufferAddress** points to.

### -field LogBufferAddress

[in] Pointer to an array of [**DXGK_FLIPQUEUE_LOG_ENTRY**](ns-d3dkmddi-dxgk_flipqueue_log_entry.md) structures in the flip queue log buffer. This value is the kernel-mode CPU virtual address of the flip queue log buffer in non-paged memory. **LogBufferAddress** is NULL if the OS is about to destroy the current flip queue log buffer.

## -remarks

See [Obtaining present statistics for queued flips](/windows-hardware/drivers/display/hardware-flip-queue#obtaining-present-statistics-for-queued-flips) for more information.

## -see-also

[**DXGK_FLIPQUEUE_LOG_ENTRY**](ns-d3dkmddi-dxgk_flipqueue_log_entry.md)

[**DXGKDDI_SETFLIPQUEUELOGBUFFER**](nc-d3dkmddi-dxgkddi_setflipqueuelogbuffer.md)
