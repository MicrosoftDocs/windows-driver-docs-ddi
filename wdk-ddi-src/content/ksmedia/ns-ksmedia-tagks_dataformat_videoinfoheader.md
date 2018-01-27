---
UID: NS:ksmedia.tagKS_DATAFORMAT_VIDEOINFOHEADER
title: tagKS_DATAFORMAT_VIDEOINFOHEADER
author: windows-driver-content
description: The KS_DATAFORMAT_VIDEOINFOHEADER structure describes a video stream that does not include bob or weave settings.
old-location: stream\ks_dataformat_videoinfoheader.htm
old-project: stream
ms.assetid: 60a04887-d696-42b2-95af-cce1c0bc102b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: *PKS_DATAFORMAT_VIDEOINFOHEADER, vidcapstruct_756be7d3-2dca-4e93-a113-7ee3871f3107.xml, PKS_DATAFORMAT_VIDEOINFOHEADER structure pointer [Streaming Media Devices], stream.ks_dataformat_videoinfoheader, PKS_DATAFORMAT_VIDEOINFOHEADER, ksmedia/KS_DATAFORMAT_VIDEOINFOHEADER, ksmedia/PKS_DATAFORMAT_VIDEOINFOHEADER, tagKS_DATAFORMAT_VIDEOINFOHEADER, KS_DATAFORMAT_VIDEOINFOHEADER structure [Streaming Media Devices], KS_DATAFORMAT_VIDEOINFOHEADER
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
-	KS_DATAFORMAT_VIDEOINFOHEADER
product: Windows
targetos: Windows
req.typenames: *PKS_DATAFORMAT_VIDEOINFOHEADER, KS_DATAFORMAT_VIDEOINFOHEADER
---

# tagKS_DATAFORMAT_VIDEOINFOHEADER structure


## -description


The KS_DATAFORMAT_VIDEOINFOHEADER structure describes a video stream that does not include bob or weave settings.


## -syntax


````
typedef struct tagKS_DATAFORMAT_VIDEOINFOHEADER {
  KSDATAFORMAT       DataFormat;
  KS_VIDEOINFOHEADER VideoInfoHeader;
} KS_DATAFORMAT_VIDEOINFOHEADER, *PKS_DATAFORMAT_VIDEOINFOHEADER;
````


## -struct-fields




### -field DataFormat

Specifies the data format.


### -field VideoInfoHeader

Specifies the details of the video stream.


## -remarks


This format is used for most capture output streams.

Minidrivers that must specify a data format that contains settings for bob or weave must use the <a href="..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader2.md">KS_DATAFORMAT_VIDEOINFOHEADER2</a> structure.



## -see-also

<a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader.md">KS_VIDEOINFOHEADER</a>

<a href="..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader2.md">KS_DATAFORMAT_VIDEOINFOHEADER2</a>

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATAFORMAT_VIDEOINFOHEADER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

