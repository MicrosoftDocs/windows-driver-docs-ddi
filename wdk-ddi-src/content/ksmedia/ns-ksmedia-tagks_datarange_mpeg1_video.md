---
UID: NS:ksmedia.tagKS_DATARANGE_MPEG1_VIDEO
title: tagKS_DATARANGE_MPEG1_VIDEO
author: windows-driver-content
description: The KS_DATARANGE_MPEG1_VIDEO structure describes the range of MPEG-1 video formats available for a stream.
old-location: stream\ks_datarange_mpeg1_video.htm
old-project: stream
ms.assetid: 0b715c9b-9a5a-4ef6-b3cc-c17964e55bc1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_DATARANGE_MPEG1_VIDEO, *PKS_DATARANGE_MPEG1_VIDEO, PKS_DATARANGE_MPEG1_VIDEO, ksmedia/PKS_DATARANGE_MPEG1_VIDEO, ksmedia/KS_DATARANGE_MPEG1_VIDEO, KS_DATARANGE_MPEG1_VIDEO structure [Streaming Media Devices], PKS_DATARANGE_MPEG1_VIDEO structure pointer [Streaming Media Devices], vidcapstruct_caa12154-017f-4796-bc84-3c132475a75e.xml, stream.ks_datarange_mpeg1_video, tagKS_DATARANGE_MPEG1_VIDEO
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
-	KS_DATARANGE_MPEG1_VIDEO
product: Windows
targetos: Windows
req.typenames: "*PKS_DATARANGE_MPEG1_VIDEO, KS_DATARANGE_MPEG1_VIDEO"
---

# tagKS_DATARANGE_MPEG1_VIDEO structure


## -description


The KS_DATARANGE_MPEG1_VIDEO structure describes the range of MPEG-1 video formats available for a stream.


## -syntax


````
typedef struct tagKS_DATARANGE_MPEG1_VIDEO {
  KSDATARANGE                 DataRange;
  BOOL                        bFixedSizeSamples;
  BOOL                        bTemporalCompression;
  DWORD                       StreamDescriptionFlags;
  DWORD                       MemoryAllocationFlags;
  KS_VIDEO_STREAM_CONFIG_CAPS ConfigCaps;
  KS_MPEG1VIDEOINFO           VideoInfoHeader;
} KS_DATARANGE_MPEG1_VIDEO, *PKS_DATARANGE_MPEG1_VIDEO;
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


## -see-also

<a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a>



<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>



<a href="..\ksmedia\ns-ksmedia-tagks_mpeg1videoinfo.md">KS_MPEG1VIDEOINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_MPEG1_VIDEO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

