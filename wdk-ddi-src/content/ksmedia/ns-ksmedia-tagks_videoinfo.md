---
UID: NS:ksmedia.tagKS_VIDEOINFO
title: tagKS_VIDEOINFO (ksmedia.h)
description: The KS_VIDEOINFO structure describes the bitmap and color information for a video stream.
old-location: stream\ks_videoinfo.htm
tech.root: stream
ms.assetid: e588a844-0b20-418c-9c65-e85f3a992d5c
ms.date: 04/23/2018
keywords: ["tagKS_VIDEOINFO structure"]
ms.keywords: "*PKS_VIDEOINFO, KS_VIDEOINFO, KS_VIDEOINFO structure [Streaming Media Devices], PKS_VIDEOINFO, PKS_VIDEOINFO structure pointer [Streaming Media Devices], ksmedia/KS_VIDEOINFO, ksmedia/PKS_VIDEOINFO, stream.ks_videoinfo, tagKS_VIDEOINFO, vidcapstruct_66265491-9578-4165-941b-432184388ea2.xml"
f1_keywords:
 - "ksmedia/KS_VIDEOINFO"
 - "KS_VIDEOINFO"
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
- KS_VIDEOINFO
targetos: Windows
req.typenames: KS_VIDEOINFO, *PKS_VIDEOINFO
---

# tagKS_VIDEOINFO structure


## -description


The KS_VIDEOINFO structure describes the bitmap and color information for a video stream.


## -struct-fields




### -field rcSource

Specifies a clipping rectangle that selects the portion of the active video signal to use. 


### -field rcTarget

Specifies a rectangle that indicates which part of the target buffer to use.


### -field dwBitRate

Specifies a value that indicates the video stream's approximate data rate, in bits per second.


### -field dwBitErrorRate

Specifies a value that indicates the video stream's data error rate, in bit errors per second.


### -field AvgTimePerFrame

Specifies the average time per frame in 100-nanosecond units.


### -field bmiHeader

Describes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader">KS_BITMAPINFOHEADER</a> structure that contains color and dimension information about the video image bitmap.


### -field bmiColors

Array of KS_RGBQUAD structures that specifies the video's color palette. Each structure represents a single color, which is a combination of red, green, and blue intensities.


### -field dwBitMasks

Array of DWORD values that specify true-color bitmasks.


### -field TrueColorInfo


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tag_ks_truecolorinfo">KS_TRUECOLORINFO</a> structure that contains both a color palette and an array of color bitmasks.


## -remarks



This structure must not be used unless the <b>biSize</b> member of the KS_BITMAPINFOHEADER member is set to <b>sizeof</b>(KS_BITMAPINFOHEADER).

A source filter can request that the sink filter take only a section of the video by providing values that effectively define a clipping rectangle in the <b>rcSource</b> member. However, if the sink filter does not check for the clipping rectangle on connection, the sink filter simply renders all of the video, effectively ignoring any clipping information passed from the source filter to the sink filter.

Ideally, a sink filter checks <b>rcSource</b> and if the sink filter does not support image extraction and the rectangle is <i>not</i> empty, then it rejects the connection. A filter should use the Win32 function <b>SetRectEmpty</b> to reset a rectangle to all zeros (and <b>IsRectEmpty</b> to later check the rectangle).

The <b>rcTarget</b> member specifies the destination rectangle for the video. Most source filters set this member to all zeros. A downstream filter can request that the video be placed in a particular area of the buffers it supplies. In this case, it calls the Win32 function <b>QueryAccept</b> with a nonempty target.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader">KS_BITMAPINFOHEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_rgbquad">KS_RGBQUAD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tag_ks_truecolorinfo">KS_TRUECOLORINFO</a>
 

 

