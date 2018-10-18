---
UID: NS:ksmedia.tagKS_DATARANGE_VIDEO_VBI
title: tagKS_DATARANGE_VIDEO_VBI
author: windows-driver-content
description: The KS_DATARANGE_VIDEO_VBI structure describes a range of data formats containing vertical blanking interval (VBI) data.
old-location: stream\ks_datarange_video_vbi.htm
tech.root: stream
ms.assetid: 83801ea2-1beb-4b73-8906-ffefee67a2ac
ms.date: 4/23/2018
ms.keywords: "*PKS_DATARANGE_VIDEO_VBI, KS_DATARANGE_VIDEO_VBI, KS_DATARANGE_VIDEO_VBI structure [Streaming Media Devices], PKS_DATARANGE_VIDEO_VBI, PKS_DATARANGE_VIDEO_VBI structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_VIDEO_VBI, ksmedia/PKS_DATARANGE_VIDEO_VBI, stream.ks_datarange_video_vbi, tagKS_DATARANGE_VIDEO_VBI, vidcapstruct_79d2aa9b-f3b9-4faf-b06e-6048686602a5.xml"
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
-	KS_DATARANGE_VIDEO_VBI
product:
- Windows
targetos: Windows
req.typenames: KS_DATARANGE_VIDEO_VBI, *PKS_DATARANGE_VIDEO_VBI
---

# tagKS_DATARANGE_VIDEO_VBI structure


## -description


The KS_DATARANGE_VIDEO_VBI structure describes a range of data formats containing vertical blanking interval (VBI) data.


## -struct-fields




### -field DataRange

Specifies major, minor, and specifier identifiers of the range of formats being described.


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


### -field VBIInfoHeader

Indicates VBI-specific information for the range of formats being described.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567692">KS_VBIINFOHEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567706">KS_VIDEO_STREAM_CONFIG_CAPS</a>
 

 

