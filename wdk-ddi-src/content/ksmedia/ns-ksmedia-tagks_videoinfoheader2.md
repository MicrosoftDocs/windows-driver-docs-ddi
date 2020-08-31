---
UID: NS:ksmedia.tagKS_VIDEOINFOHEADER2
title: tagKS_VIDEOINFOHEADER2 (ksmedia.h)
description: The KS_VIDEOINFOHEADER2 structure describes the details of a video stream, including bob or weave settings, copy protection, and pixel aspect ratio.
old-location: stream\ks_videoinfoheader2.htm
tech.root: stream
ms.assetid: 4eb909fe-7ba2-4208-b713-54252022a5cf
ms.date: 08/20/2020
keywords: ["tagKS_VIDEOINFOHEADER2 structure"]
ms.keywords: "*PKS_VIDEOINFOHEADER2, KS_VIDEOINFOHEADER2, KS_VIDEOINFOHEADER2 structure [Streaming Media Devices], PKS_VIDEOINFOHEADER2, PKS_VIDEOINFOHEADER2 structure pointer [Streaming Media Devices], ksmedia/KS_VIDEOINFOHEADER2, ksmedia/PKS_VIDEOINFOHEADER2, stream.ks_videoinfoheader2, tagKS_VIDEOINFOHEADER2, vidcapstruct_c789f606-9b19-42b0-8492-3b945141c274.xml"
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
req.typenames: KS_VIDEOINFOHEADER2, *PKS_VIDEOINFOHEADER2
f1_keywords:
 - tagKS_VIDEOINFOHEADER2
 - ksmedia/tagKS_VIDEOINFOHEADER2
 - PKS_VIDEOINFOHEADER2
 - ksmedia/PKS_VIDEOINFOHEADER2
 - KS_VIDEOINFOHEADER2
 - ksmedia/KS_VIDEOINFOHEADER2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_VIDEOINFOHEADER2
---

# tagKS_VIDEOINFOHEADER2 structure


## -description

The KS_VIDEOINFOHEADER2 structure describes the details of a video stream, including bob or weave settings, copy protection, and pixel aspect ratio.

## -struct-fields

### -field rcSource

Specifies a clipping rectangle that selects the portion of the active video signal to use.

### -field rcTarget

Specifies a rectangle that indicates what part of the target buffer to use.

### -field dwBitRate

Specifies a value that indicates the video stream's appropriate data rate, in bits per second.

### -field dwBitErrorRate

Specifies a value that indicates the video stream's data error rate, in bit errors per second.

### -field AvgTimePerFrame

Specifies the average time per frame, in 100-nanosecond units.

### -field dwInterlaceFlags

Specifies interlace information. Undefined flags must be set to zero, or the connection may be rejected. This member can be set to one or more (logical OR) values that are defined in *ksmedia.h*:

| Flag | Description |
|--|--|
| KS_INTERLACE_IsInterlaced | Indicates an interlace stream. If 0, then the other KS_INTERLACE_Xxx bits are irrelevant. |
| KS_INTERLACE_1FieldPerSample | Indicates one field per media sample. If zero, indicates two fields per media sample. |
| KS_INTERLACE_Field1First | Indicates that Field 1 is first. If zero, indicates that Field 2 is first. Top field in PAL is Field 1, top field in NTSC is Field 2. |
| KS_INTERLACE_UNUSED | Unused |
| KS_INTERLACE_FieldPatternMask | Indicates the bits used to specify field pattern. |
| KS_INTERLACE_FieldPatField1Only | Indicates that a stream never contains a Field 2. |
| KS_INTERLACE_FieldPatField2Only | Indicates that a stream never contains a Field 1. |
| KS_INTERLACE_FieldPatBothRegular | Indicates that there will be a Field 2 for every Field 1. |
| KS_INTERLACE_FieldPatBothIrregular | Indicates a random pattern of Field 1s and Field 2s. |
| KS_INTERLACE_DisplayModeMask | Invalid for video capture. |
| KS_INTERLACE_DisplayModeBobOnly | Invalid for video capture. |
| KS_INTERLACE_DisplayModeWeaveOnly | Invalid for video capture. |
| KS_INTERLACE_DisplayModeBobOrWeave | Invalid for video capture. |

### -field dwCopyProtectFlags

Specifies a KSCOPYPROTECTRestrictDuplication value (0x00000001) to indicate if duplication of a stream should be restricted. If undefined, specify zero or the connection will be rejected.

### -field dwPictAspectRatioX

Specifies the *x* dimension of the picture-aspect ratio (for example, 16 for a 16 × 9 display). The value is expressed in inches-by-inches, not pixels-by-pixels.

### -field dwPictAspectRatioY

Specifies the *y* dimension of the picture aspect ratio (for example, 9 for 16 × 9 display). The value is expressed in inches-by-inches, not pixels-by-pixels.

### -field dwControlFlags

In operating systems prior to Windows Vista, this member was named **dwReserved1** and was required to be zero. In Windows Vista, **dwReserved1** was combined in a union with a new member named **dwControlFlags**. If used, **dwControlFlags** contains a bitwise OR of the flags in the following table.

| Value | Description |
|--|--|
| AMCONTROL_USED | Indicates the **dwControlFlags** flags are used. |
| AMCONTROL_PAD_TO_4x3 | The image should be padded and displayed in a 4 x 3 area. |
| AMCONTROL_PAD_TO_16x9 | The image should be padded and displayed in a 16 x 9 area. |
| AMCONTROL_COLORINFO_PRESENT | Additional color information is contained in the upper 24 bits of the **dwControlFlags** field. |

The AMCONTROL_USED flag provides backward compatibility with older filters. If the AMCONTROL_USED flag is not set, the remaining bits in this field should be ignored. If a filter uses any other flags, it should set the AMCONTROL_USED flag.

The two AMCONTROL_PAD_xxx flags are used by decoders to determine the aspect ratio of the output rectangle.

If the AMCONTROL_COLORINFO_PRESENT flag is set, it means the upper 24 bits of the dwControlFlags field are treated as a [DXVA_ExtendedFormat](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat) structure.

See the Remarks section later in this topic for more information about **dwControlFlags**.

### -field dwReserved1

This member is for backward compatibility. See **dwControlFlags** for more information.

### -field dwReserved2

Reserved for system use. Must be set to zero or the connection will be rejected.

### -field bmiHeader

Indicates a [KS_BITMAPINFOHEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader) structure that contains color and dimension information for the video image bitmap.

## -remarks

To describe a video stream without bob or weave settings, use [KS_VIDEOINFOHEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfoheader).

The KS_VIDEOINFOHEADER2 structure is identical to the DirectShow [VIDEOINFOHEADER2](https://docs.microsoft.com/previous-versions//ms787914(v=vs.85)) structure.

Capture minidrivers that produce video fields (instead of frames) must use the [KS_DATARANGE_VIDEO2](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_datarange_video2) structure, which contains the KS_VIDEOINFOHEADER2 structure.

A source filter can request that the sink filter take only a section of the video by providing values that effectively define a clipping rectangle in the **rcSource** member. However, if the sink filter does not check for the clipping rectangle on connection, the sink filter simply renders all of the video, effectively ignoring any clipping information passed from the source filter to the sink filter.

Ideally, a sink filter checks **rcSource** and if the sink filter does not support image extraction, and the rectangle is *not* empty, then it rejects the connection. A filter should use the Win32 function **SetRectEmpty** to reset a rectangle to all zeros (and set **IsRectEmpty** to later check the rectangle).

The **rcTarget** member specifies the destination rectangle for the video. Most source filters set this member to all zeros. A downstream filter can request that the video be placed in a particular area of the buffers that it supplies. In this case, it calls the Win32 function **QueryAccept** with a nonempty target.

If the AMCONTROL_COLORINFO_PRESENT flag is set in the **dwControlFlags** member, you can cast the **dwControlFlags** value to a [DXVA_ExtendedFormat](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat) structure to access the extended color information. For more information, see [VIDEOINFOHEADER2](https://docs.microsoft.com/previous-versions//ms787914(v=vs.85)).

## -see-also

[KS_BITMAPINFOHEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader)

[KS_DATARANGE_VIDEO2](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_datarange_video2)

[KS_VIDEOINFOHEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfoheader)

