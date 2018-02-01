---
UID: NS:ksmedia.tagKS_DATARANGE_VIDEO
title: tagKS_DATARANGE_VIDEO
author: windows-driver-content
description: The KS_DATARANGE_VIDEO structure describes a range of video streams without bob or weave settings.
old-location: stream\ks_datarange_video.htm
old-project: stream
ms.assetid: 682fe2b7-3166-4691-8959-ec7f34c414f7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/KS_DATARANGE_VIDEO, tagKS_DATARANGE_VIDEO, PKS_DATARANGE_VIDEO structure pointer [Streaming Media Devices], stream.ks_datarange_video, PKS_DATARANGE_VIDEO, vidcapstruct_1ea64e7e-bfcd-444c-a6e9-914f20fb2172.xml, KS_DATARANGE_VIDEO structure [Streaming Media Devices], KS_DATARANGE_VIDEO, *PKS_DATARANGE_VIDEO, ksmedia/PKS_DATARANGE_VIDEO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KS_DATARANGE_VIDEO
product: Windows
targetos: Windows
req.typenames: KS_DATARANGE_VIDEO, *PKS_DATARANGE_VIDEO
---

# tagKS_DATARANGE_VIDEO structure


## -description


The KS_DATARANGE_VIDEO structure describes a range of video streams without bob or weave settings.


## -syntax


````
typedef struct tagKS_DATARANGE_VIDEO {
  KSDATARANGE                 DataRange;
  BOOL                        bFixedSizeSamples;
  BOOL                        bTemporalCompression;
  DWORD                       StreamDescriptionFlags;
  DWORD                       MemoryAllocationFlags;
  KS_VIDEO_STREAM_CONFIG_CAPS ConfigCaps;
  KS_VIDEOINFOHEADER          VideoInfoHeader;
} KS_DATARANGE_VIDEO, *PKS_DATARANGE_VIDEO;
````


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
</ol>For example, a stream that supports RGB16, RGB24, YVU9, and JPEG capture formats defines an array of four KS_DATAFORMAT_VIDEO structures. 



## -see-also

<a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a>

<a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader.md">KS_VIDEOINFOHEADER</a>

<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_VIDEO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

