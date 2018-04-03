---
UID: NS:ksmedia.tagKS_DATARANGE_H264_VIDEO
title: tagKS_DATARANGE_H264_VIDEO
author: windows-driver-content
description: The KS_DATARANGE_H264_VIDEO structure describes the range of MPEG-2 video formats available for a stream.
old-location: stream\ks_datarange_h264_video.htm
old-project: stream
ms.assetid: E52B252F-0530-4543-A44C-95D4198504CA
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DATARANGE_H264_VIDEO, KS_DATARANGE_H264_VIDEO, KS_DATARANGE_H264_VIDEO structure [Streaming Media Devices], PKS_DATARANGE_H264_VIDEO, PKS_DATARANGE_H264_VIDEO structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_H264_VIDEO, ksmedia/PKS_DATARANGE_H264_VIDEO, stream.ks_datarange_h264_video, tagKS_DATARANGE_H264_VIDEO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ksmedia.h
api_name:
-	KS_DATARANGE_H264_VIDEO
product:
- Windows
targetos: Windows
req.typenames: KS_DATARANGE_H264_VIDEO, *PKS_DATARANGE_H264_VIDEO
---

# tagKS_DATARANGE_H264_VIDEO structure


## -description


The KS_DATARANGE_H264_VIDEO structure describes the range of MPEG-2 video formats available for a stream.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464008">KS_H264VIDEOINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567706">KS_VIDEO_STREAM_CONFIG_CAPS</a>
 

 

