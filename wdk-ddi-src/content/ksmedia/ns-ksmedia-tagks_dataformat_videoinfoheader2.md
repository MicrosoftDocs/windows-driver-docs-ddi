---
UID: NS:ksmedia.tagKS_DATAFORMAT_VIDEOINFOHEADER2
title: tagKS_DATAFORMAT_VIDEOINFOHEADER2 (ksmedia.h)
description: The KS_DATAFORMAT_VIDEOINFOHEADER2 structure describes a video stream that includes settings for bob or weave.
old-location: stream\ks_dataformat_videoinfoheader2.htm
tech.root: stream
ms.assetid: 92deaecd-69d7-4e64-bdb0-a2736add0c2f
ms.date: 04/23/2018
keywords: ["tagKS_DATAFORMAT_VIDEOINFOHEADER2 structure"]
ms.keywords: "*PKS_DATAFORMAT_VIDEOINFOHEADER2, KS_DATAFORMAT_VIDEOINFOHEADER2, KS_DATAFORMAT_VIDEOINFOHEADER2 structure [Streaming Media Devices], PKS_DATAFORMAT_VIDEOINFOHEADER2, PKS_DATAFORMAT_VIDEOINFOHEADER2 structure pointer [Streaming Media Devices], ksmedia/KS_DATAFORMAT_VIDEOINFOHEADER2, ksmedia/PKS_DATAFORMAT_VIDEOINFOHEADER2, stream.ks_dataformat_videoinfoheader2, tagKS_DATAFORMAT_VIDEOINFOHEADER2, vidcapstruct_cadaf63f-50d5-41c5-926b-81724dddb890.xml"
f1_keywords:
 - "ksmedia/KS_DATAFORMAT_VIDEOINFOHEADER2"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KS_DATAFORMAT_VIDEOINFOHEADER2
product:
- Windows
targetos: Windows
req.typenames: KS_DATAFORMAT_VIDEOINFOHEADER2, *PKS_DATAFORMAT_VIDEOINFOHEADER2
---

# tagKS_DATAFORMAT_VIDEOINFOHEADER2 structure


## -description


The KS_DATAFORMAT_VIDEOINFOHEADER2 structure describes a video stream that includes settings for bob or weave.


## -struct-fields




### -field DataFormat

Specifies the data format.


### -field VideoInfoHeader2

Specifies the details of the video stream, including options for specifying bob or weave settings.


## -remarks



Minidrivers that do not need to specify bob or weave settings may use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_dataformat_videoinfoheader">KS_DATAFORMAT_VIDEOINFOHEADER</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_dataformat_videoinfoheader">KS_DATAFORMAT_VIDEOINFOHEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfoheader">KS_VIDEOINFOHEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfoheader2">KS_VIDEOINFOHEADER2</a>
 

 

