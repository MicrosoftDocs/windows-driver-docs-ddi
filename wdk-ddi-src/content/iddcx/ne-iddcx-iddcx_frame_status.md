---
UID: NE:iddcx.IDDCX_FRAME_STATUS
title: IDDCX_FRAME_STATUS (iddcx.h)
description: Defines the processing status of the frame.
old-location: display\iddcx_frame_status.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_FRAME_STATUS enumeration"]
ms.keywords: IDDCX_FRAME_STATUS, IDDCX_FRAME_STATUS enumeration [Display Devices], IDDCX_FRAME_STATUS_COMPLETED, IDDCX_FRAME_STATUS_DROPPED, IDDCX_FRAME_STATUS_ERROR, IDDCX_FRAME_STATUS_UNINITIALIZED, display.iddcx_frame_status, iddcx/IDDCX_FRAME_STATUS, iddcx/IDDCX_FRAME_STATUS_COMPLETED, iddcx/IDDCX_FRAME_STATUS_DROPPED, iddcx/IDDCX_FRAME_STATUS_ERROR, iddcx/IDDCX_FRAME_STATUS_UNINITIALIZED
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: 
f1_keywords:
 - IDDCX_FRAME_STATUS
 - iddcx/IDDCX_FRAME_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_FRAME_STATUS
---

# IDDCX_FRAME_STATUS enumeration

## -description

A **IDDCX_FRAME_STATUS** value indicates the processing status of the frame.

## -enum-fields

### -field IDDCX_FRAME_STATUS_UNINITIALIZED:0

Indicates that an **IDDCX_FRAME_STATUS** variable has not yet been assigned a meaningful value.

### -field IDDCX_FRAME_STATUS_COMPLETED:1

Indicates that the frame was processed completely and sent to the device.

### -field IDDCX_FRAME_STATUS_DROPPED:2

Indicates that the driver stopped processing this frame to start on a newer frame. This normally happens if it is taking a long time to process/transmit the frame.

### -field IDDCX_FRAME_STATUS_ERROR:3

Indicates that the driver stopped processing this frame because the driver hit an internal error.

## -see-also

[**IDDCX_FRAME_STATISTICS**](ns-iddcx-iddcx_frame_statistics.md)

[**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md)

[**IddCxSwapChainReleaseAndAcquireSystemBuffer**](nf-iddcx-iddcxswapchainreleaseandacquiresystembuffer.md)
