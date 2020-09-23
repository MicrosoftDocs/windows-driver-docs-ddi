---
UID: NS:ksmedia.tagKS_DATARANGE_VIDEO2
title: tagKS_DATARANGE_VIDEO2 (ksmedia.h)
description: The KS_DATARANGE_VIDEO2 structure describes a video stream including bob or weave settings.
old-location: stream\ks_datarange_video2.htm
tech.root: stream
ms.assetid: bddb19cb-7705-470b-ad22-14fd72f3db11
ms.date: 04/23/2018
keywords: ["tagKS_DATARANGE_VIDEO2 structure"]
ms.keywords: "*PKS_DATARANGE_VIDEO2, KS_DATARANGE_VIDEO2, KS_DATARANGE_VIDEO2 structure [Streaming Media Devices], PKS_DATARANGE_VIDEO2, PKS_DATARANGE_VIDEO2 structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_VIDEO2, ksmedia/PKS_DATARANGE_VIDEO2, stream.ks_datarange_video2, tagKS_DATARANGE_VIDEO2, vidcapstruct_f014ea98-b1a5-4d05-aea3-b13e7a3f5918.xml"
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
req.typenames: KS_DATARANGE_VIDEO2, *PKS_DATARANGE_VIDEO2
f1_keywords:
 - tagKS_DATARANGE_VIDEO2
 - ksmedia/tagKS_DATARANGE_VIDEO2
 - PKS_DATARANGE_VIDEO2
 - ksmedia/PKS_DATARANGE_VIDEO2
 - KS_DATARANGE_VIDEO2
 - ksmedia/KS_DATARANGE_VIDEO2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_DATARANGE_VIDEO2
---

# tagKS_DATARANGE_VIDEO2 structure


## -description

The KS_DATARANGE_VIDEO2 structure describes a video stream including bob or weave settings.

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

## -remarks

This structure should be used instead of a <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_datarange_video">KS_DATARANGE_VIDEO</a> structure when a minidriver must describe content with bob or weave settings.

## -see-also

<a href="/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfoheader2">KS_VIDEOINFOHEADER2</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ks_video_stream_config_caps">KS_VIDEO_STREAM_CONFIG_CAPS</a>