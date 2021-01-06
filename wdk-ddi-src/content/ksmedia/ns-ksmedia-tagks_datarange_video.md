---
UID: NS:ksmedia.tagKS_DATARANGE_VIDEO
title: tagKS_DATARANGE_VIDEO (ksmedia.h)
description: The KS_DATARANGE_VIDEO structure describes a range of video streams without bob or weave settings.
old-location: stream\ks_datarange_video.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["tagKS_DATARANGE_VIDEO structure"]
ms.keywords: "*PKS_DATARANGE_VIDEO, KS_DATARANGE_VIDEO, KS_DATARANGE_VIDEO structure [Streaming Media Devices], PKS_DATARANGE_VIDEO, PKS_DATARANGE_VIDEO structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_VIDEO, ksmedia/PKS_DATARANGE_VIDEO, stream.ks_datarange_video, tagKS_DATARANGE_VIDEO, vidcapstruct_1ea64e7e-bfcd-444c-a6e9-914f20fb2172.xml"
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
req.typenames: KS_DATARANGE_VIDEO, *PKS_DATARANGE_VIDEO
f1_keywords:
 - tagKS_DATARANGE_VIDEO
 - ksmedia/tagKS_DATARANGE_VIDEO
 - PKS_DATARANGE_VIDEO
 - ksmedia/PKS_DATARANGE_VIDEO
 - KS_DATARANGE_VIDEO
 - ksmedia/KS_DATARANGE_VIDEO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_DATARANGE_VIDEO
---

# tagKS_DATARANGE_VIDEO structure


## -description

The KS_DATARANGE_VIDEO structure describes a range of video streams without bob or weave settings.

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

The KS_DATARANGE_VIDEO structure is used for two related purposes:

<ol>
<li>
At minidriver initialization time, the minidriver returns an array of KS_DATARANGE_VIDEO structures exposing all the supported formats for a given pin, including possible cropping and scaling options.

</li>
<li>
When a particular format is selected by a user-mode client, the members (and their settings) of this structure determine whether a proposed format is supported by the minidriver. User-mode clients modify the contents of the <b>VideoInfoHeader</b> member but must leave all other members of KS_DATARANGE_VIDEO unchanged. The minidriver then verifies the requested parameters and returns a KS_DATAFORMAT_VIDEO structure. The minidriver then calculates members that are unique to the particular format requested. 

</li>
</ol>
For example, a stream that supports RGB16, RGB24, YVU9, and JPEG capture formats defines an array of four KS_DATAFORMAT_VIDEO structures.

## -see-also

<a href="/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfoheader">KS_VIDEOINFOHEADER</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ks_video_stream_config_caps">KS_VIDEO_STREAM_CONFIG_CAPS</a>
