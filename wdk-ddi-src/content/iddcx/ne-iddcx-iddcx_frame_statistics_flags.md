---
UID: NE:iddcx.IDDCX_FRAME_STATISTICS_FLAGS
title: IDDCX_FRAME_STATISTICS_FLAGS (iddcx.h)
description: Indicates whether a frame was altered by the driver.
old-location: display\iddcx_frame_statistics_flags.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_FRAME_STATISTICS_FLAGS enumeration"]
ms.keywords: IDDCX_FRAME_STATISTICS_FLAGS, IDDCX_FRAME_STATISTICS_FLAGS enumeration [Display Devices], IDDCX_FRAME_STATISTICS_FLAGS_NONE, IDDCX_FRAME_STATISTICS_FLAGS_REDUCED_COLOR_FIDELITY, display.iddcx_frame_statistics_flags, iddcx/IDDCX_FRAME_STATISTICS_FLAGS, iddcx/IDDCX_FRAME_STATISTICS_FLAGS_NONE, iddcx/IDDCX_FRAME_STATISTICS_FLAGS_REDUCED_COLOR_FIDELITY
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
 - IDDCX_FRAME_STATISTICS_FLAGS
 - iddcx/IDDCX_FRAME_STATISTICS_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_FRAME_STATISTICS_FLAGS
---

# IDDCX_FRAME_STATISTICS_FLAGS enumeration

## -description

A **IDDCX_FRAME_STATISTICS_FLAGS** value indicates how a frame was altered by the driver.

## -enum-fields

### -field IDDCX_FRAME_STATISTICS_FLAGS_NONE:0

Indicates that there are no alterations to the frame.

### -field IDDCX_FRAME_STATISTICS_FLAGS_REDUCED_COLOR_FIDELITY:1

When set indicates that the driver reduced the color fidelity of the desktop image while processing and transmitting this frame.

## -see-also

[**IDDCX_FRAME_STATISTICS**](ns-iddcx-iddcx_frame_statistics.md)
