---
UID: NS:ksmedia.tagKS_DATARANGE_MPEG1_VIDEO
title: tagKS_DATARANGE_MPEG1_VIDEO (ksmedia.h)
description: The KS_DATARANGE_MPEG1_VIDEO structure describes the range of MPEG-1 video formats available for a stream.
old-location: stream\ks_datarange_mpeg1_video.htm
tech.root: stream
ms.assetid: 0b715c9b-9a5a-4ef6-b3cc-c17964e55bc1
ms.date: 04/23/2018
keywords: ["tagKS_DATARANGE_MPEG1_VIDEO structure"]
ms.keywords: "*PKS_DATARANGE_MPEG1_VIDEO, KS_DATARANGE_MPEG1_VIDEO, KS_DATARANGE_MPEG1_VIDEO structure [Streaming Media Devices], PKS_DATARANGE_MPEG1_VIDEO, PKS_DATARANGE_MPEG1_VIDEO structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_MPEG1_VIDEO, ksmedia/PKS_DATARANGE_MPEG1_VIDEO, stream.ks_datarange_mpeg1_video, tagKS_DATARANGE_MPEG1_VIDEO, vidcapstruct_caa12154-017f-4796-bc84-3c132475a75e.xml"
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
req.typenames: KS_DATARANGE_MPEG1_VIDEO, *PKS_DATARANGE_MPEG1_VIDEO
f1_keywords:
 - tagKS_DATARANGE_MPEG1_VIDEO
 - ksmedia/tagKS_DATARANGE_MPEG1_VIDEO
 - PKS_DATARANGE_MPEG1_VIDEO
 - ksmedia/PKS_DATARANGE_MPEG1_VIDEO
 - KS_DATARANGE_MPEG1_VIDEO
 - ksmedia/KS_DATARANGE_MPEG1_VIDEO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_DATARANGE_MPEG1_VIDEO
---

# tagKS_DATARANGE_MPEG1_VIDEO structure


## -description

The KS_DATARANGE_MPEG1_VIDEO structure describes the range of MPEG-1 video formats available for a stream.

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

### -field VideoInfoHeader

Specifies the details of the video stream.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_mpeg1videoinfo">KS_MPEG1VIDEOINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ks_video_stream_config_caps">KS_VIDEO_STREAM_CONFIG_CAPS</a>

