---
UID: NF:ksproxy.IKsPin.KsQueryMediums
title: IKsPin::KsQueryMediums (ksproxy.h)
description: The KsQueryMediums method retrieves mediums that a pin supports.
old-location: stream\ikspin_ksquerymediums.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsPin::KsQueryMediums"]
ms.keywords: IKsPin interface [Streaming Media Devices],KsQueryMediums method, IKsPin.KsQueryMediums, IKsPin::KsQueryMediums, KsQueryMediums, KsQueryMediums method [Streaming Media Devices], KsQueryMediums method [Streaming Media Devices],IKsPin interface, ksproxy/IKsPin::KsQueryMediums, ksproxy_88debe31-2dd5-41bc-80c0-164b28dc586f.xml, stream.ikspin_ksquerymediums
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - IKsPin::KsQueryMediums
 - ksproxy/IKsPin::KsQueryMediums
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsPin.KsQueryMediums
---

# IKsPin::KsQueryMediums


## -description

The <b>KsQueryMediums</b> method retrieves mediums that a pin supports.

## -parameters

### -param MediumList 

[out]
Pointer to a buffer that receives a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a> structure, followed by a sequence of <a href="/previous-versions/ff563538(v=vs.85)">KSPIN_MEDIUM</a> structures that describe medium types. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

The returned mediums are ordered by preference. 

Applications call <b>KsQueryMediums</b> to retrieve mediums that pins support in order to build a filter graph.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a>



<a href="/previous-versions/ff563538(v=vs.85)">KSPIN_MEDIUM</a>
