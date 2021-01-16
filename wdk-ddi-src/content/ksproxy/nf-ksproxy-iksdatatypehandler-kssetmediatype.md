---
UID: NF:ksproxy.IKsDataTypeHandler.KsSetMediaType
title: IKsDataTypeHandler::KsSetMediaType (ksproxy.h)
description: The KsSetMediaType method sets the media type for a data type handler.
old-location: stream\iksdatatypehandler_kssetmediatype.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsDataTypeHandler::KsSetMediaType"]
ms.keywords: IKsDataTypeHandler interface [Streaming Media Devices],KsSetMediaType method, IKsDataTypeHandler.KsSetMediaType, IKsDataTypeHandler::KsSetMediaType, KsSetMediaType, KsSetMediaType method [Streaming Media Devices], KsSetMediaType method [Streaming Media Devices],IKsDataTypeHandler interface, ksproxy/IKsDataTypeHandler::KsSetMediaType, ksproxy_5992cc35-8912-4e1e-8712-ebb6f36f5193.xml, stream.iksdatatypehandler_kssetmediatype
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
 - IKsDataTypeHandler::KsSetMediaType
 - ksproxy/IKsDataTypeHandler::KsSetMediaType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsDataTypeHandler::KsSetMediaType
---

# IKsDataTypeHandler::KsSetMediaType


## -description

The <b>KsSetMediaType</b> method sets the media type for a data type handler.

## -parameters

### -param AmMediaType

#### - MediaType [in]

Pointer to a <b>CMediaType</b> object associated with the media type.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

Clients can call <b>KsSetMediaType</b> of a single data type handler to initialize this data type handler to a particular media type from a group of many disparate media types.

For more information about <b>CMediaType</b> class, see the Microsoft Windows SDK documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksdatatypehandler">IKsDataTypeHandler</a>

