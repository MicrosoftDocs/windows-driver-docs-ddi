---
UID: NS:avcstrm.tagKS_DATARANGE_DV_AVC
title: tagKS_DATARANGE_DV_AVC (avcstrm.h)
description: The KS_DATARANGE_DV_AVC structure stores a range of AV/C digital video formats.
old-location: stream\ks_datarange_dv_avc.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["tagKS_DATARANGE_DV_AVC structure"]
ms.keywords: "*PKS_DATARANGE_DV_AVC, KS_DATARANGE_DV_AVC, KS_DATARANGE_DV_AVC structure [Streaming Media Devices], PKS_DATARANGE_DV_AVC, PKS_DATARANGE_DV_AVC structure pointer [Streaming Media Devices], avcsref_e5ebf0ed-91f2-415a-a6b1-346cfebf16b5.xml, avcstrm/KS_DATARANGE_DV_AVC, avcstrm/PKS_DATARANGE_DV_AVC, stream.ks_datarange_dv_avc, tagKS_DATARANGE_DV_AVC"
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
req.typenames: KS_DATARANGE_DV_AVC, *PKS_DATARANGE_DV_AVC
f1_keywords:
 - tagKS_DATARANGE_DV_AVC
 - avcstrm/tagKS_DATARANGE_DV_AVC
 - PKS_DATARANGE_DV_AVC
 - avcstrm/PKS_DATARANGE_DV_AVC
 - KS_DATARANGE_DV_AVC
 - avcstrm/KS_DATARANGE_DV_AVC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avcstrm.h
api_name:
 - KS_DATARANGE_DV_AVC
---

# tagKS_DATARANGE_DV_AVC structure


## -description

The KS_DATARANGE_DV_AVC structure stores a range of AV/C digital video formats.

## -struct-fields

### -field DataRange

Specifies the range of supported AV/C digital video formats.

### -field DVVideoInfo

Specifies the digital video information, for example, sound tracks and video information.

### -field ConnectInfo

Specifies the AV/C preconnection info.

## -see-also

<a href="/windows-hardware/drivers/ddi/avc/ns-avc-_avcpreconnectinfo">AVCPRECONNECTINFO</a>



<a href="/windows-hardware/drivers/ddi/avcstrm/ns-avcstrm-_dvinfo">DVINFO</a>



<a href="/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>
