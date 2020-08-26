---
UID: NF:ksproxy.IKsDataTypeHandler.KsIsMediaTypeInRanges
title: IKsDataTypeHandler::KsIsMediaTypeInRanges (ksproxy.h)
description: The KsIsMediaTypeInRanges method validates that a media type is within the provided data ranges.
old-location: stream\iksdatatypehandler_ksismediatypeinranges.htm
tech.root: stream
ms.assetid: 354dcd2b-fa63-4574-94d8-149e3f199751
ms.date: 04/23/2018
keywords: ["IKsDataTypeHandler::KsIsMediaTypeInRanges"]
ms.keywords: IKsDataTypeHandler interface [Streaming Media Devices],KsIsMediaTypeInRanges method, IKsDataTypeHandler.KsIsMediaTypeInRanges, IKsDataTypeHandler::KsIsMediaTypeInRanges, KsIsMediaTypeInRanges, KsIsMediaTypeInRanges method [Streaming Media Devices], KsIsMediaTypeInRanges method [Streaming Media Devices],IKsDataTypeHandler interface, ksproxy/IKsDataTypeHandler::KsIsMediaTypeInRanges, ksproxy_ebd4f24e-02a2-4228-b11b-890693ece498.xml, stream.iksdatatypehandler_ksismediatypeinranges
f1_keywords:
 - "ksproxy/IKsDataTypeHandler.KsIsMediaTypeInRanges"
 - "IKsDataTypeHandler.KsIsMediaTypeInRanges"
req.header: ksproxy.h
req.include-header: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsDataTypeHandler.KsIsMediaTypeInRanges
targetos: Windows
req.typenames: 
---

# IKsDataTypeHandler::KsIsMediaTypeInRanges


## -description


The <b>KsIsMediaTypeInRanges</b> method validates that a media type is within the provided data ranges.


## -parameters




### -param DataRanges 
[in]
Pointer to a buffer that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a> structure, followed by a sequence of extensible <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structures, aligned on 64-bit boundaries. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



A client first calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-kssetmediatype">IKsDataTypeHandler::KsSetMediaType</a> method to assign a media type that the client references in subsequent operations on the data type handler. The client then calls <b>KsIsMediaTypeInRanges</b> to validate that the media type is within particular data ranges. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-kssetmediatype">IKsDataTypeHandler::KsSetMediaType</a>



<a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a>
 

 

