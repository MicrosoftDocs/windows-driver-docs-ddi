---
UID: NS:avcstrm.tagKS_DATARANGE_DVVIDEO
title: tagKS_DATARANGE_DVVIDEO
author: windows-driver-content
description: The KS_DATARANGE_DV_AVC structure stores a range of digital video formats.
old-location: stream\ks_datarange_dvvideo.htm
old-project: stream
ms.assetid: 89cbb950-c3e5-4d79-aa7f-fd64cd67fd5e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKS_DATARANGE_DVVIDEO, KS_DATARANGE_DVVIDEO, *PKS_DATARANGE_DVVIDEO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_DATARANGE_DVVIDEO
req.alt-loc: avcstrm.h
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
req.typenames: KS_DATARANGE_DVVIDEO, *PKS_DATARANGE_DVVIDEO
---

# tagKS_DATARANGE_DVVIDEO structure



## -description
The KS_DATARANGE_DV_AVC structure stores a range of digital video formats.



## -syntax

````
typedef struct tagKS_DATARANGE_DVVIDEO {
  KSDATARANGE DataRange;
  DVINFO      DVVideoInfo;
} KS_DATARANGE_DVVIDEO, *PKS_DATARANGE_DVVIDEO;
````


## -struct-fields

### -field DataRange

Specifies the range of supported digital video formats.


### -field DVVideoInfo

Specifies the digital video information, for example, sound tracks and video information.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>
</dt>
<dt>
<a href="..\avcstrm\ns-avcstrm-_dvinfo.md">DVINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_DVVIDEO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

