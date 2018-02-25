---
UID: NS:ksmedia.tagKS_DATAFORMAT_H264VIDEOINFO
title: tagKS_DATAFORMAT_H264VIDEOINFO
author: windows-driver-content
description: The KS_DATAFORMAT_H264VIDEOINFO structure describes the data formats range available for a stream.
old-location: stream\ks_dataformat_h264videoinfo.htm
old-project: stream
ms.assetid: 6D2C0245-542E-4749-B8F3-531BFA3800E3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKS_DATAFORMAT_H264VIDEOINFO, ,, 2, 4, 6, A, D, E, F, H, I, K, KS_DATAFORMAT_H264VIDEOINFO, KS_DATAFORMAT_H264VIDEOINFO structure [Streaming Media Devices], M, N, O, P, PKS_DATAFORMAT_H264VIDEOINFO, PKS_DATAFORMAT_H264VIDEOINFO structure pointer [Streaming Media Devices], R, S, T, V, _, a, g, ksmedia/KS_DATAFORMAT_H264VIDEOINFO, ksmedia/PKS_DATAFORMAT_H264VIDEOINFO, stream.ks_dataformat_h264videoinfo, t, tagKS_DATAFORMAT_H264VIDEOINFO"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KS_DATAFORMAT_H264VIDEOINFO
product: Windows
targetos: Windows
req.typenames: KS_DATAFORMAT_H264VIDEOINFO, *PKS_DATAFORMAT_H264VIDEOINFO
---

# tagKS_DATAFORMAT_H264VIDEOINFO structure


## -description


The KS_DATAFORMAT_H264VIDEOINFO structure describes the data formats range available for a stream.


## -syntax


````
typedef struct _KS_DATAFORMAT_H264VIDEOINFO {
  KSDATAFORMAT                     DataFormat;
     KS_H264VIDEOINFO              H264VideoInfoHeader;
} KS_DATAFORMAT_H264VIDEOINFO, *PKS_DATAFORMAT_H264VIDEOINFO;
````


## -struct-fields




### -field DataFormat

Specifies the major identifier for the format. 


### -field H264VideoInfoHeader

Specifies the details of the video stream.


## -see-also

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>



<a href="..\ksmedia\ns-ksmedia-tagks_h264videoinfo.md">KS_H264VIDEOINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATAFORMAT_H264VIDEOINFO structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

