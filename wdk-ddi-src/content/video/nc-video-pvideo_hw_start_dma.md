---
UID: NC:video.PVIDEO_HW_START_DMA
tech.root: display
title: PVIDEO_HW_START_DMA
ms.date: 11/01/2024
targetos: Windows
description: Learn more about the PVIDEO_HW_START_DMA function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: video.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - video.h
api_name:
 - PVIDEO_HW_START_DMA
f1_keywords:
 - PVIDEO_HW_START_DMA
 - video/PVIDEO_HW_START_DMA
dev_langs:
 - c++
helpviewer_keywords:
 - PVIDEO_HW_START_DMA
---

## -description

A video miniport driver's **HwStartDma** function starts a DMA transfer. Reserved for system use.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see [Device Extensions](/windows-hardware/drivers/kernel/device-extensions).

### -param pDma

Opaque type for DMA handle.

## -returns

**HwStartDma** returns a HW_DMA_RETURN enumeration value.

## -see-also

[**VIDEO_HW_INITIALIZATION_DATA**](ns-video-_video_hw_initialization_data.md)
