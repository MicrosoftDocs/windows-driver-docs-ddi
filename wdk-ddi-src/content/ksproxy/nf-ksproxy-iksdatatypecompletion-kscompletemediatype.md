---
UID: NF:ksproxy.IKsDataTypeCompletion.KsCompleteMediaType
title: IKsDataTypeCompletion::KsCompleteMediaType (ksproxy.h)
description: The KsCompleteMediaType method completes a partially-specified media type that was first presented to the IAMStreamConfig::SetFormat method.
old-location: stream\iksdatatypecompletion_kscompletemediatype.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsDataTypeCompletion::KsCompleteMediaType"]
ms.keywords: IKsDataTypeCompletion interface [Streaming Media Devices],KsCompleteMediaType method, IKsDataTypeCompletion.KsCompleteMediaType, IKsDataTypeCompletion::KsCompleteMediaType, KsCompleteMediaType, KsCompleteMediaType method [Streaming Media Devices], KsCompleteMediaType method [Streaming Media Devices],IKsDataTypeCompletion interface, ksproxy/IKsDataTypeCompletion::KsCompleteMediaType, ksproxy_950cbba2-9512-46d0-ac08-133195e4370f.xml, stream.iksdatatypecompletion_kscompletemediatype
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
 - IKsDataTypeCompletion::KsCompleteMediaType
 - ksproxy/IKsDataTypeCompletion::KsCompleteMediaType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsDataTypeCompletion::KsCompleteMediaType
---

# IKsDataTypeCompletion::KsCompleteMediaType


## -description

The <b>KsCompleteMediaType</b> method completes a partially-specified media type that was first presented to the <b>IAMStreamConfig::SetFormat</b> method.

## -parameters

### -param FilterHandle 

[in]
Handle to the underlying KS filter.

### -param PinFactoryId 

[in]
Identifier of the pin factory against which the media type is being completed.

### -param AmMediaType 

[in, out]
Pointer to a AM_MEDIA_TYPE structure that describes the format of the media samples. <b>KsCompleteMediaType</b> receives partially specified media samples, completes the specification, and returns.

## -returns

Returns NOERROR if successful and the media type was completed; otherwise, returns an error code.

## -remarks

The <b>KsCompleteMediaType</b> method is primarily used for video media types, in which the <b>biSizeImage</b> member of the <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader">KS_BITMAPINFOHEADER</a> structure is known only to the driver, because of the private compression formats supported. If required, the data type handler can query the underlying KS filter in order to complete the given media type. 

When the proxy creates an instance of the data type handler for purposes of completing a media type, the proxy passes the media type to the <a href="/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-kssetmediatype">IKsDataTypeHandler::KsSetMediaType</a> method to first initialize this data type handler to the particular media type. 

For more information about <b>IAMStreamConfig::SetFormat</b> and AM_MEDIA_TYPE, see the Microsoft Windows SDK documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksdatatypehandler-kssetmediatype">IKsDataTypeHandler::KsSetMediaType</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_bitmapinfoheader">KS_BITMAPINFOHEADER</a>

