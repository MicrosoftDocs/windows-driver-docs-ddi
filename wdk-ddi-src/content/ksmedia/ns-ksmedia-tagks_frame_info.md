---
UID: NS:ksmedia.tagKS_FRAME_INFO
title: tagKS_FRAME_INFO (ksmedia.h)
description: The KS_FRAME_INFO structure extends the KSSTREAM_HEADER structure for video streams.
old-location: stream\ks_frame_info.htm
tech.root: stream
ms.assetid: 7c2ebe5d-ecb0-41d2-a1bb-7e131ea350a7
ms.date: 04/23/2018
keywords: ["tagKS_FRAME_INFO structure"]
ms.keywords: "*PKS_FRAME_INFO, KS_FRAME_INFO, KS_FRAME_INFO structure [Streaming Media Devices], PKS_FRAME_INFO, PKS_FRAME_INFO structure pointer [Streaming Media Devices], ksmedia/KS_FRAME_INFO, ksmedia/PKS_FRAME_INFO, stream.ks_frame_info, tagKS_FRAME_INFO, vidcapstruct_1ce3f0b4-3032-4956-83a3-2a92039eb7a0.xml"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
req.typenames: KS_FRAME_INFO, *PKS_FRAME_INFO
ms.custom: 19H1
f1_keywords:
 - tagKS_FRAME_INFO
 - ksmedia/tagKS_FRAME_INFO
 - PKS_FRAME_INFO
 - ksmedia/PKS_FRAME_INFO
 - KS_FRAME_INFO
 - ksmedia/KS_FRAME_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_FRAME_INFO
---

# tagKS_FRAME_INFO structure


## -description

The **KS_FRAME_INFO** structure extends the [KSSTREAM_HEADER](../ks/ns-ks-ksstream_header.md) structure for video streams.

## -struct-fields

### -field ExtendedHeaderSize

Specifies the size of this structure, in bytes.

### -field dwFrameFlags

Specifies flags indicating additional information about the frame captured. During capture, the minidriver sets this member to one of the following values that are defined in *ksmedia.h*:

| Flag | Meaning |
| --- | --- |
| KS_VIDEO_FLAG_FRAME | Indicates a complete frame. |
| KS_VIDEO_FLAG_FIELD1 | Indicates Field 1 of a two-field sequence. |
| KS_VIDEO_FLAG_FIELD2 | Indicates Field 2 of a two-field sequence. |
| KS_VIDEO_FLAG_I_FRAME | Indicates that this frame can be completely decoded without reference to any other frames. |
| KS_VIDEO_FLAG_P_FRAME | Indicates that this is a predicted frame. |
| KS_VIDEO_FLAG_B_FRAME | Indicates that this is a bidirectional frame. |

### -field PictureNumber

Specifies a count representing the current picture number. Initialize or update this value on transition into KSSTATE_ACQUIRE.

### -field DropCount

Specifies the number of pictures that were not captured. During capture, the minidriver sets this member. This counter should be incremented whenever a frame should have been captured but was not; this condition usually arises when no buffers were available during capture. Initialize or update this value on transition into KSSTATE_ACQUIRE.

### -field hDirectDraw

Specifies the user-mode handle to DirectDraw. This handle is only provided to the minidriver when capturing to a DirectDraw surface for preview or overlay purposes.

### -field hSurfaceHandle

Specifies the user-mode handle to the DirectDraw surface. This handle is only provided to the minidriver when capturing to a DirectDraw surface for preview or overlay purposes.

### -field DirectDrawRect

Specifies the portion of the DirectDraw surface that has been locked. This is normally the entire surface.

### -field lSurfacePitch

Contains surface pitch a.k.a stride

### -field Reserved1

Reserved and should not be used by the minidriver.

### -field Reserved2

Reserved and should not be used by the minidriver.

### -field Reserved4

Reserved and should not be used by the minidriver.

### -field FrameCompletionNumber

An identifying sequence number for the frame in the completed queue. This number is used to verify proper frame order. When this value is 0, the frame was cancelled.

This member is available starting with Windows 8.1.

## -remarks

The KS_FRAME_INFO structure provides a way to return information about the frame captured, as well as a way to pass Microsoft DirectDraw handles used when capturing to a DirectDraw surface.

The **PictureNumber** member count represents the count of the current picture, which is calculated in one of two ways depending on the device:

* Measure the time since the stream was started and divide by the frame duration. This method is appropriate for devices that do not provide their own clock. For example:

    ```cpp
    PictureNumber = ElapsedTime / FrameDuration;
    ```

* Add together the count of frames captured and the count of frame dropped. This method is appropriate for devices that provide their own clock. For example:

    ```cpp
    PictureNumber = FramesCaptured + FramesDropped;
    ```

When calculating **PictureNumber** and **DropCount**, it is important to use the frame duration specified when the stream was opened, which may not necessarily match the rate at which the device is actually producing images. For example, a USB camera may only produce images at 7.5 fps, but a client could open the stream at 8 fps. In this case, all calculations should use the 8 fps number.

For more information about updating **PictureNumber** and **DropCount** see [Capturing Video](/windows-hardware/drivers/stream/capturing-video).

## -see-also

[KSSTREAM_HEADER](../ks/ns-ks-ksstream_header.md)