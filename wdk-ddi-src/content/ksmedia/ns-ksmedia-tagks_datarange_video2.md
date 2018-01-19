---
UID: NS:ksmedia.tagKS_DATARANGE_VIDEO2
title: tagKS_DATARANGE_VIDEO2
author: windows-driver-content
description: The KS_DATARANGE_VIDEO2 structure describes a video stream including bob or weave settings.
old-location: stream\ks_datarange_video2.htm
old-project: stream
ms.assetid: bddb19cb-7705-470b-ad22-14fd72f3db11
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKS_DATARANGE_VIDEO2, *PKS_DATARANGE_VIDEO2, KS_DATARANGE_VIDEO2
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
req.alt-api: KS_DATARANGE_VIDEO2
req.alt-loc: ksmedia.h
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
req.typenames: *PKS_DATARANGE_VIDEO2, KS_DATARANGE_VIDEO2
---

# tagKS_DATARANGE_VIDEO2 structure



## -description
The KS_DATARANGE_VIDEO2 structure describes a video stream including bob or weave settings.



## -syntax

````
typedef struct tagKS_DATARANGE_VIDEO2 {
  KSDATARANGE                 DataRange;
  BOOL                        bFixedSizeSamples;
  BOOL                        bTemporalCompression;
  DWORD                       StreamDescriptionFlags;
  DWORD                       MemoryAllocationFlags;
  KS_VIDEO_STREAM_CONFIG_CAPS ConfigCaps;
  KS_VIDEOINFOHEADER2         VideoInfoHeader;
} KS_DATARANGE_VIDEO2, *PKS_DATARANGE_VIDEO2;
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
This structure should be used instead of a <a href="..\ksmedia\ns-ksmedia-tagks_datarange_video.md">KS_DATARANGE_VIDEO</a> structure when a minidriver must describe content with bob or weave settings.


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader2.md">KS_VIDEOINFOHEADER2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_VIDEO2 structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

