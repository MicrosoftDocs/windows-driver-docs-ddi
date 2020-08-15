---
UID: NF:ksproxy.KsResolveRequiredAttributes
title: KsResolveRequiredAttributes function (ksproxy.h)
description: The KsResolveRequiredAttributes function searches the attributes list that is attached to a data range for specified attributes and ensures that all specified attributes were found.
old-location: stream\ksresolverequiredattributes.htm
tech.root: stream
ms.assetid: 04153845-4170-40db-ba60-3d438ae0a60d
ms.date: 04/23/2018
keywords: ["KsResolveRequiredAttributes function"]
ms.keywords: KsResolveRequiredAttributes, KsResolveRequiredAttributes function [Streaming Media Devices], ksproxy/KsResolveRequiredAttributes, ksproxy_fb22470c-5445-4005-b1c3-4f708cc0a47f.xml, stream.ksresolverequiredattributes
f1_keywords:
 - "ksproxy/KsResolveRequiredAttributes"
 - "KsResolveRequiredAttributes"
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ksproxy.lib
- Ksproxy.dll
api_name:
- KsResolveRequiredAttributes
targetos: Windows
req.typenames: 
---

# KsResolveRequiredAttributes function


## -description


The <b>KsResolveRequiredAttributes</b> function searches the attributes list that is attached to a data range for specified attributes and ensures that all specified attributes were found. 


## -parameters




### -param DataRange 
[in]
Pointer to a <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structure that possibly has an attached attribute list. <b>KsResolveRequiredAttributes</b> searches the data range's attribute list for the attributes at <i>Attributes</i>. An attribute list attached to a data range follows that data range.


### -param Attributes 
[in, optional]
Pointer to a buffer that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a> structure, followed by a sequence of KSATTRIBUTE structures that describe attributes. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header. If this pointer is <b>NULL</b>, then <b>KsResolveRequiredAttributes</b> only succeeds if <i>DataRange</i> does not have an attached attribute list.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksattribute">KSATTRIBUTE</a>



<a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a>
 

 

