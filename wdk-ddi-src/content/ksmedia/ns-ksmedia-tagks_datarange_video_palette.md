---
UID: NS:ksmedia.tagKS_DATARANGE_VIDEO_PALETTE
title: tagKS_DATARANGE_VIDEO_PALETTE (ksmedia.h)
description: The KS_DATARANGE_VIDEO_PALETTE structure describes a stream and its color capabilities.
old-location: stream\ks_datarange_video_palette.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["tagKS_DATARANGE_VIDEO_PALETTE structure"]
ms.keywords: "*PKS_DATARANGE_VIDEO_PALETTE, KS_DATARANGE_VIDEO_PALETTE, KS_DATARANGE_VIDEO_PALETTE structure [Streaming Media Devices], PKS_DATARANGE_VIDEO_PALETTE, PKS_DATARANGE_VIDEO_PALETTE structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_VIDEO_PALETTE, ksmedia/PKS_DATARANGE_VIDEO_PALETTE, stream.ks_datarange_video_palette, tagKS_DATARANGE_VIDEO_PALETTE, vidcapstruct_8bba39d4-8ffb-41df-b314-f63fe26d66fa.xml"
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
req.typenames: KS_DATARANGE_VIDEO_PALETTE, *PKS_DATARANGE_VIDEO_PALETTE
f1_keywords:
 - tagKS_DATARANGE_VIDEO_PALETTE
 - ksmedia/tagKS_DATARANGE_VIDEO_PALETTE
 - PKS_DATARANGE_VIDEO_PALETTE
 - ksmedia/PKS_DATARANGE_VIDEO_PALETTE
 - KS_DATARANGE_VIDEO_PALETTE
 - ksmedia/KS_DATARANGE_VIDEO_PALETTE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKS_DATARANGE_VIDEO_PALETTE
 - PKS_DATARANGE_VIDEO_PALETTE
 - KS_DATARANGE_VIDEO_PALETTE
---

# tagKS_DATARANGE_VIDEO_PALETTE structure


## -description

The KS_DATARANGE_VIDEO_PALETTE structure describes a stream and its color capabilities.

## -struct-fields

### -field DataRange

Specifies the major identifier for the format.

### -field bFixedSizeSamples

Specifies that all the samples are the same size if set to <b>TRUE</b>.

### -field bTemporalCompression

Specifies whether each sample can stand independently on its own, without relying on previous or future samples.

### -field StreamDescriptionFlags

Unused and should be set to zero.

### -field MemoryAllocationFlags

Unused and should be set to zero.

### -field ConfigCaps

Specifies the configuration of the stream, including scaling, cropping, and frame and data rates.

### -field VideoInfo

Specifies the details of the video stream.

## -see-also

<a href="/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfo">KS_VIDEOINFO</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ks_video_stream_config_caps">KS_VIDEO_STREAM_CONFIG_CAPS</a>

