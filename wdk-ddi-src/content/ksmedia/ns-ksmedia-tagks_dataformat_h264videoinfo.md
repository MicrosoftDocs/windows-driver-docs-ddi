---
UID: NS:ksmedia.tagKS_DATAFORMAT_H264VIDEOINFO
title: tagKS_DATAFORMAT_H264VIDEOINFO
author: windows-driver-content
description: The KS_DATAFORMAT_H264VIDEOINFO structure describes the data formats range available for a stream.
old-location: stream\ks_dataformat_h264videoinfo.htm
old-project: stream
ms.assetid: 6D2C0245-542E-4749-B8F3-531BFA3800E3
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DATAFORMAT_H264VIDEOINFO, KS_DATAFORMAT_H264VIDEOINFO, KS_DATAFORMAT_H264VIDEOINFO structure [Streaming Media Devices], PKS_DATAFORMAT_H264VIDEOINFO, PKS_DATAFORMAT_H264VIDEOINFO structure pointer [Streaming Media Devices], ksmedia/KS_DATAFORMAT_H264VIDEOINFO, ksmedia/PKS_DATAFORMAT_H264VIDEOINFO, stream.ks_dataformat_h264videoinfo, tagKS_DATAFORMAT_H264VIDEOINFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ksmedia.h
api_name:
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



 

 


