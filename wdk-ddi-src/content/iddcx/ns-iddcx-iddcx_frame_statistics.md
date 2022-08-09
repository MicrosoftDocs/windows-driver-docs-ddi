---
UID: NS:iddcx.IDDCX_FRAME_STATISTICS
title: IDDCX_FRAME_STATISTICS (iddcx.h)
description: Gives information about the current frame being processed.
old-location: display\iddcx_frame_statistics.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_FRAME_STATISTICS structure"]
ms.keywords: IDDCX_FRAME_STATISTICS, IDDCX_FRAME_STATISTICS structure [Display Devices], display.iddcx_frame_statistics, iddcx/IDDCX_FRAME_STATISTICS
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
 - IDDCX_FRAME_STATISTICS
 - iddcx/IDDCX_FRAME_STATISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_FRAME_STATISTICS
---

# IDDCX_FRAME_STATISTICS structure

## -description

The **IDDCX_FRAME_STATISTICS** structure provides information about the current frame being processed.

## -struct-fields

### -field Size

Total size of this structure, in bytes.

### -field PresentationFrameNumber

The frame number provided in a prior call to [**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md) (or [**IddCxSwapChainReleaseAndAcquireSystemBuffer**](nf-iddcx-iddcxswapchainreleaseandacquiresystembuffer.md)).

### -field FrameStatus

An [**IDDCX_FRAME_STATUS**](ne-iddcx-iddcx_frame_status.md) value that indicates the overall status of processing this frame.

### -field ReEncodeNumber

A zero-based number to indicate the number of times the same frame has been encoded and sent. Re-encodes can be the result of the OS providing the same frame and frame number to the driver to encode or the driver having to re-encode outside of the normal OS presentation to satisfy the protocol.

### -field FrameSliceTotal

The number of slices the driver processes the frame in. If slices are not used, then this should be set to the value one.

### -field CurrentSlice

The zero-based slice number being reported. If slicing is not supported, then the driver should always set this to the value zero.

### -field FrameAcquireQpcTime

System QPC time at which the driver acquired the buffer from the OS.

### -field FrameProcessingStepsCount

The size of the frame step array pointed to by **pFrameProcessingStep**.

### -field pFrameProcessingStep

An array of [**IDDCX_FRAME_STATISTICS_STEP**](ns-iddcx-iddcx_frame_statistics_step.md) structures that describe the frame processing steps the driver performed.

### -field SendStartQpcTime

Marks the time when the driver started transmission for this slice to the device. **SendStartQpcTime** marks the time the driver started calling the transmit APIs, not when the data actually starts being transmitted.

### -field SendStopQpcTime

Marks the time when the driver stopped transmission for this slice to the device. **SendStopQpcTime** marks the time the driver stopped calling the transmit APIs, not when the data actually stops being transmitted.

### -field SendCompleteQpcTime

Marks the time when the send was reported as complete by the OS. This is an optional time stamp that can be used if the driver uses an asynchronous transmit API and a completion routine. In the event the driver does not have an asynchronous completion routine, this value should be set to zero.

### -field Flags

A [**IDDCX_FRAME_STATISTICS_FLAGS**](ne-iddcx-iddcx_frame_statistics_flags.md) value that indicates how the frame was altered by the driver.

### -field ProcessedPixelCount

The total number of pixels processed in this frame.

### -field FrameSizeInBytes

Total size of the data sent to the device for this frame. This value includes all the slices.

## -see-also

[**IDDCX_FRAME_STATISTICS_FLAGS**](ne-iddcx-iddcx_frame_statistics_flags.md)

[**IDDCX_FRAME_STATISTICS_STEP**](ns-iddcx-iddcx_frame_statistics_step.md)

[**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md)

[**IddCxSwapChainReleaseAndAcquireSystemBuffer**](nf-iddcx-iddcxswapchainreleaseandacquiresystembuffer.md)
