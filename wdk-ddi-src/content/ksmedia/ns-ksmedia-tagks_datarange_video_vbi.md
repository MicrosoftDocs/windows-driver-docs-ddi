---
UID: NS:ksmedia.tagKS_DATARANGE_VIDEO_VBI
title: tagKS_DATARANGE_VIDEO_VBI
author: windows-driver-content
description: The KS_DATARANGE_VIDEO_VBI structure describes a range of data formats containing vertical blanking interval (VBI) data.
old-location: stream\ks_datarange_video_vbi.htm
old-project: stream
ms.assetid: 83801ea2-1beb-4b73-8906-ffefee67a2ac
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_DATARANGE_VIDEO_VBI structure [Streaming Media Devices], ksmedia/KS_DATARANGE_VIDEO_VBI, KS_DATARANGE_VIDEO_VBI, ksmedia/PKS_DATARANGE_VIDEO_VBI, PKS_DATARANGE_VIDEO_VBI structure pointer [Streaming Media Devices], stream.ks_datarange_video_vbi, vidcapstruct_79d2aa9b-f3b9-4faf-b06e-6048686602a5.xml, tagKS_DATARANGE_VIDEO_VBI, *PKS_DATARANGE_VIDEO_VBI, PKS_DATARANGE_VIDEO_VBI
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
-	KS_DATARANGE_VIDEO_VBI
product: Windows
targetos: Windows
req.typenames: KS_DATARANGE_VIDEO_VBI, *PKS_DATARANGE_VIDEO_VBI
---

# tagKS_DATARANGE_VIDEO_VBI structure


## -description


The KS_DATARANGE_VIDEO_VBI structure describes a range of data formats containing vertical blanking interval (VBI) data.


## -syntax


````
typedef struct tagKS_DATARANGE_VIDEO_VBI {
  KSDATARANGE                 DataRange;
  BOOL                        bFixedSizeSamples;
  BOOL                        bTemporalCompression;
  DWORD                       StreamDescriptionFlags;
  DWORD                       MemoryAllocationFlags;
  KS_VIDEO_STREAM_CONFIG_CAPS ConfigCaps;
  KS_VBIINFOHEADER            VBIInfoHeader;
} KS_DATARANGE_VIDEO_VBI, *PKS_DATARANGE_VIDEO_VBI;
````


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

<a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a>

<a href="..\ksmedia\ns-ksmedia-tagks_vbiinfoheader.md">KS_VBIINFOHEADER</a>

<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_VIDEO_VBI structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

