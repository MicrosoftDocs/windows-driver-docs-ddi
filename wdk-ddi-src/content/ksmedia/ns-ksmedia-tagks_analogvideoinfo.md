---
UID: NS:ksmedia.tagKS_AnalogVideoInfo
title: tagKS_AnalogVideoInfo (ksmedia.h)
description: The KS_ANALOGVIDEOINFO structure describes an analog video stream.
old-location: stream\ks_analogvideoinfo.htm
tech.root: stream
ms.assetid: a3562a08-c567-4bb5-9de2-aaa561687b88
ms.date: 04/23/2018
keywords: ["tagKS_AnalogVideoInfo structure"]
ms.keywords: "*PKS_ANALOGVIDEOINFO, KS_ANALOGVIDEOINFO, KS_ANALOGVIDEOINFO structure [Streaming Media Devices], PKS_ANALOGVIDEOINFO, PKS_ANALOGVIDEOINFO structure pointer [Streaming Media Devices], ksmedia/KS_ANALOGVIDEOINFO, ksmedia/PKS_ANALOGVIDEOINFO, stream.ks_analogvideoinfo, tagKS_AnalogVideoInfo, vidcapstruct_1a351d21-929d-4a84-863a-cf590d82c16b.xml"
f1_keywords:
 - "ksmedia/KS_ANALOGVIDEOINFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KS_ANALOGVIDEOINFO
product:
- Windows
targetos: Windows
req.typenames: KS_ANALOGVIDEOINFO, *PKS_ANALOGVIDEOINFO
---

# tagKS_AnalogVideoInfo structure


## -description


The KS_ANALOGVIDEOINFO structure describes an analog video stream.


## -struct-fields




### -field rcSource

Specifies a clipping rectangle that selects the portion of the active video signal to use. 


### -field rcTarget

Specifies a rectangle that indicates which part of the target buffer to use.


### -field dwActiveWidth

Specifies the width of the active incoming video signal. For example, the value for ITUR-601 could be set to 720 active samples per line.


### -field dwActiveHeight

Specifies the height of the active incoming video signal. For example, the value for NTSC could be set to 483. For PAL/SECAM, the value could be set to 575.


### -field AvgTimePerFrame

Specifies the average time per frame, in 100-nanosecond units.


## -remarks



A source filter can request that the sink filter take only a section of the video by providing values that effectively define a clipping rectangle in the <b>rcSource</b> member. However, if the sink filter does not check for the clipping rectangle on connection, the sink filter simply renders all of the video, effectively ignoring any clipping information passed from the source filter to the sink filter.

Ideally, a sink filter checks <b>rcSource</b>. If the sink filter does not support image extraction, and the rectangle is <i>not</i> empty, then it rejects the connection. A filter should use the Win32 function <b>SetRectEmpty</b> to reset a rectangle to all zeros (and set <b>IsRectEmpty</b> to later check the rectangle).

The <b>rcTarget</b> member specifies the destination rectangle for the video. Most source filters set this member to all zeros. A downstream filter can request that the video be placed in a particular area of the buffers it supplies. In this case, it calls the Win32 function <b>QueryAccept</b> with a nonempty target.



