---
UID: NS:ksmedia.tagKS_DATARANGE_ANALOGVIDEO
title: tagKS_DATARANGE_ANALOGVIDEO
author: windows-driver-content
description: The KS_DATARANGE_ANALOGVIDEO structure describes an analog video stream.
old-location: stream\ks_datarange_analogvideo.htm
old-project: stream
ms.assetid: e89e9108-28a1-46ac-8694-047a656dcb74
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKS_DATARANGE_ANALOGVIDEO, ,, A, D, E, G, I, K, KS_DATARANGE_ANALOGVIDEO, KS_DATARANGE_ANALOGVIDEO structure [Streaming Media Devices], L, N, O, P, PKS_DATARANGE_ANALOGVIDEO, PKS_DATARANGE_ANALOGVIDEO structure pointer [Streaming Media Devices], R, S, T, V, _, a, g, ksmedia/KS_DATARANGE_ANALOGVIDEO, ksmedia/PKS_DATARANGE_ANALOGVIDEO, stream.ks_datarange_analogvideo, t, tagKS_DATARANGE_ANALOGVIDEO, vidcapstruct_43f72b11-2ac7-4b68-b595-c37022d956c7.xml"
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
-	KS_DATARANGE_ANALOGVIDEO
product: Windows
targetos: Windows
req.typenames: KS_DATARANGE_ANALOGVIDEO, *PKS_DATARANGE_ANALOGVIDEO
---

# tagKS_DATARANGE_ANALOGVIDEO structure


## -description


The KS_DATARANGE_ANALOGVIDEO structure describes an analog video stream.


## -syntax


````
typedef struct tagKS_DATARANGE_ANALOGVIDEO {
  KSDATARANGE        DataRange;
  KS_ANALOGVIDEOINFO AnalogVideoInfo;
} KS_DATARANGE_ANALOGVIDEO, *PKS_DATARANGE_ANALOGVIDEO;
````


## -struct-fields




### -field DataRange

Specifies the major identifier for the format.


### -field AnalogVideoInfo

Specifies the details of the analog video stream. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="..\ksmedia\ns-ksmedia-tagks_analogvideoinfo.md">KS_ANALOGVIDEOINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_ANALOGVIDEO structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

