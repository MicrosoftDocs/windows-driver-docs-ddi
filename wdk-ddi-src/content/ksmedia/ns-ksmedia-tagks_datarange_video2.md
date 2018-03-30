---
UID: NS:ksmedia.tagKS_DATARANGE_VIDEO2
title: tagKS_DATARANGE_VIDEO2
author: windows-driver-content
description: The KS_DATARANGE_VIDEO2 structure describes a video stream including bob or weave settings.
old-location: stream\ks_datarange_video2.htm
old-project: stream
ms.assetid: bddb19cb-7705-470b-ad22-14fd72f3db11
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DATARANGE_VIDEO2, KS_DATARANGE_VIDEO2, KS_DATARANGE_VIDEO2 structure [Streaming Media Devices], PKS_DATARANGE_VIDEO2, PKS_DATARANGE_VIDEO2 structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_VIDEO2, ksmedia/PKS_DATARANGE_VIDEO2, stream.ks_datarange_video2, tagKS_DATARANGE_VIDEO2, vidcapstruct_f014ea98-b1a5-4d05-aea3-b13e7a3f5918.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KS_DATARANGE_VIDEO2
product: Windows
targetos: Windows
req.typenames: KS_DATARANGE_VIDEO2, *PKS_DATARANGE_VIDEO2
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



This structure should be used instead of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567628">KS_DATARANGE_VIDEO</a> structure when a minidriver must describe content with bob or weave settings.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<<<<<<< HEAD
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567702">KS_VIDEOINFOHEADER2</a>
=======
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>
>>>>>>> parent of 2d896a8e266... Added changes



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567706">KS_VIDEO_STREAM_CONFIG_CAPS</a>
 

 

