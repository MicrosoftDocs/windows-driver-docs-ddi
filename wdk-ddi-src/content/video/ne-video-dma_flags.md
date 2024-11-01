---
UID: NE:video.DMA_FLAGS
tech.root: display
title: DMA_FLAGS
ms.date: 11/01/2024
targetos: Windows
description: Learn more about DMA_FLAGS enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: video.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - video.h
api_name:
 - DMA_FLAGS
f1_keywords:
 - DMA_FLAGS
 - video/DMA_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - DMA_FLAGS
---

## -description

The **DMA_FLAGS** enumeration specifies flags for the [**VideoPortLockPages**](nf-video-videoportlockpages.md) or [**VideoPortDoDma**](nf-video-videoportdodma.md) functions.

## -enum-fields

### -field VideoPortUnlockAfterDma

Tells the video port to unlock the pages after the miniport signals that the DMA is complete via the **pDmaCompletionEvent** in [**HwStartDma**](nc-video-pvideo_hw_start_dma.md). Failure to set this event at DMA completion can cause the memory to be unlocked at random times. This flag is best used when one wants to do one DMA transfer that occurs infrequently. It allows locking, DMAing, and unlocking to be performed in the context of one IOCTL.

### -field VideoPortKeepPagesLocked

Tells the video port to leave the pages locked if possible.

### -field VideoPortDmaInitOnly

Tells the video port to lock the pages but not call the miniport's [**HwStartDma**](nc-video-pvideo_hw_start_dma.md) routine. This flag isn't applicable to [**VideoPortDoDma**](nf-video-videoportdodma.md).

## -see-also

[**HwStartDma**](nc-video-pvideo_hw_start_dma.md)

[**VideoPortDoDma**](nf-video-videoportdodma.md)

[**VideoPortLockPages**](nf-video-videoportlockpages.md)
