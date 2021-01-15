---
UID: NS:ksmedia.tagKS_DATAFORMAT_VIDEOINFOHEADER
title: tagKS_DATAFORMAT_VIDEOINFOHEADER (ksmedia.h)
description: The KS_DATAFORMAT_VIDEOINFOHEADER structure describes a video stream that does not include bob or weave settings.
old-location: stream\ks_dataformat_videoinfoheader.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["tagKS_DATAFORMAT_VIDEOINFOHEADER structure"]
ms.keywords: "*PKS_DATAFORMAT_VIDEOINFOHEADER, KS_DATAFORMAT_VIDEOINFOHEADER, KS_DATAFORMAT_VIDEOINFOHEADER structure [Streaming Media Devices], PKS_DATAFORMAT_VIDEOINFOHEADER, PKS_DATAFORMAT_VIDEOINFOHEADER structure pointer [Streaming Media Devices], ksmedia/KS_DATAFORMAT_VIDEOINFOHEADER, ksmedia/PKS_DATAFORMAT_VIDEOINFOHEADER, stream.ks_dataformat_videoinfoheader, tagKS_DATAFORMAT_VIDEOINFOHEADER, vidcapstruct_756be7d3-2dca-4e93-a113-7ee3871f3107.xml"
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
targetos: Windows
req.typenames: KS_DATAFORMAT_VIDEOINFOHEADER, *PKS_DATAFORMAT_VIDEOINFOHEADER
f1_keywords:
 - tagKS_DATAFORMAT_VIDEOINFOHEADER
 - ksmedia/tagKS_DATAFORMAT_VIDEOINFOHEADER
 - PKS_DATAFORMAT_VIDEOINFOHEADER
 - ksmedia/PKS_DATAFORMAT_VIDEOINFOHEADER
 - KS_DATAFORMAT_VIDEOINFOHEADER
 - ksmedia/KS_DATAFORMAT_VIDEOINFOHEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKS_DATAFORMAT_VIDEOINFOHEADER
 - PKS_DATAFORMAT_VIDEOINFOHEADER
 - KS_DATAFORMAT_VIDEOINFOHEADER
---

# tagKS_DATAFORMAT_VIDEOINFOHEADER structure


## -description

The KS_DATAFORMAT_VIDEOINFOHEADER structure describes a video stream that does not include bob or weave settings.

## -struct-fields

### -field DataFormat

Specifies the data format.

### -field VideoInfoHeader

Specifies the details of the video stream.

## -remarks

This format is used for most capture output streams.

Minidrivers that must specify a data format that contains settings for bob or weave must use the <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_dataformat_videoinfoheader2">KS_DATAFORMAT_VIDEOINFOHEADER2</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_dataformat_videoinfoheader2">KS_DATAFORMAT_VIDEOINFOHEADER2</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_videoinfoheader">KS_VIDEOINFOHEADER</a>

