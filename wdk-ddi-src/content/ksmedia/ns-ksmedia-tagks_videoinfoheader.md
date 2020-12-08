---
UID: NS:ksmedia.tagKS_VIDEOINFOHEADER
title: tagKS_VIDEOINFOHEADER (ksmedia.h)
description: The KS_VIDEOINFOHEADER structure describes the bitmap and color information for a video stream.
old-location: stream\ks_videoinfoheader.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["tagKS_VIDEOINFOHEADER structure"]
ms.keywords: "*PKS_VIDEOINFOHEADER, KS_VIDEOINFOHEADER, KS_VIDEOINFOHEADER structure [Streaming Media Devices], PKS_VIDEOINFOHEADER, PKS_VIDEOINFOHEADER structure pointer [Streaming Media Devices], ksmedia/KS_VIDEOINFOHEADER, ksmedia/PKS_VIDEOINFOHEADER, stream.ks_videoinfoheader, tagKS_VIDEOINFOHEADER, vidcapstruct_785a83de-3f90-44f1-b20f-9509032e8a06.xml"
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
req.typenames: KS_VIDEOINFOHEADER, *PKS_VIDEOINFOHEADER
f1_keywords:
 - tagKS_VIDEOINFOHEADER
 - ksmedia/tagKS_VIDEOINFOHEADER
 - PKS_VIDEOINFOHEADER
 - ksmedia/PKS_VIDEOINFOHEADER
 - KS_VIDEOINFOHEADER
 - ksmedia/KS_VIDEOINFOHEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_VIDEOINFOHEADER
---

# tagKS_VIDEOINFOHEADER structure


## -description

The KS_VIDEOINFOHEADER structure describes the bitmap and color information for a video stream.

## -struct-fields

### -field rcSource

Specifies a clipping rectangle that selects the portion of the active video signal to use.

### -field rcTarget

Specifies a rectangle that defines the target destination video window.

### -field dwBitRate

Specifies a value that indicates the video stream's approximate data rate, in bits per second.

### -field dwBitErrorRate

Specifies a value that indicates the video stream's data error rate, in bit errors per second.

### -field AvgTimePerFrame

Specifies the average time per frame, in 100-nanosecond units.

### -field bmiHeader

Describes a <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader">KS_BITMAPINFOHEADER</a> structure that contains color and dimension information about the video image bitmap.

## -remarks

To describe a video stream with bob or weave settings, use <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfoheader2">KS_VIDEOINFOHEADER2</a>.

The KS_VIDEOINFOHEADER structure is identical to the Microsoft DirectShow VIDEOINFOHEADER structure.

A source filter can request that the sink filter take only a section of the video by providing values that effectively define a clipping rectangle in the <b>rcSource</b> member. However, if the sink filter does not check for the clipping rectangle on connection, the sink filter simply renders all of the video, effectively ignoring any clipping information passed from the source filter to the sink filter.

Ideally, a sink filter checks <b>rcSource</b> and if the sink filter does not support image extraction, and the rectangle is <i>not</i> empty, then it rejects the connection. A filter should use the Win32 function <b>SetRectEmpty</b> to reset a rectangle to all zeros (and set <b>IsRectEmpty</b> to later check the rectangle).

The <b>rcTarget</b> member specifies the destination rectangle for the video. Most source filters set this member to all zeros. A downstream filter can request that the video be placed in a particular area of the buffers that it supplies. In this case, it calls the Win32 function <b>QueryAccept</b> with a nonempty target.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader">KS_BITMAPINFOHEADER</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfoheader2">KS_VIDEOINFOHEADER2</a>
